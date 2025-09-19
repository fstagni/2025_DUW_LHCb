---
colorSchema: light
favicon: /public/images/diracx-logo-square.png
color: orange-light
layout: cover
routerMode: hash
title: The LHCb case
theme: neversink 
neversink_string: "The 11th DIRAC Users' Workshop"
---

![LHCb everywhere](/public/images/LHCb_everywhere.jpg)

**Federico Stagni** <Email v="federico.stagni@cern.ch" />

September 19th 2025
__ <a href="https://indico.cern.ch/e/duw11" class="ns-c-iconlink"><mdi-open-in-new />The 11th DIRAC Users' Workshop</a>  


---
layout: top-title
color: gray-light
align: c
title: reminders
---

:: title ::

# Reminders

:: content ::

- LHCb uses DIRAC(X) for managing all its distributed computing activities
- Peaking 400K concurrently running jobs
  - on WLCG Grid, opportunistic grid-like sites, SSH-accessed clusters, HPCs, and the HLT farm
  - not using any cloud
- Using storage at the Tier0 (disk+tape), 8 Tier1 (disk+tape), a dozen Tier2D (disk)
  - Mostly sending the jobs where there's the data


---
layout: top-title
color: gray-light
align: c
title: reminders2
---

:: title ::

# Reminders/2

:: content ::

- DIRAC is extended in LHCbDIRAC
  - For interacting with "the Bookkeeping", which is a provenance database with an Oracle backend
  - For TransformationSystem plugins
  - For the ProductionSystem, which adds logic on top of the TS
- WebAppDIRAC is extended in LHCbWebDIRAC, basically because of the bookkeeping
- Pilot is extended in LHCbPilot for adding few minor Pilot commands

So, for DiracX:
- lhcbdiracx extends diracx
- lhcbdiracx-web extends diracx-web

---
layout: top-title
color: gray-light
align: c
title: reminders3
---

:: title ::

# Reminders/3

:: content ::

- The vast majority of the jobs we run are production jobs
  - and the vast majority of those are MonteCarlo simulation
- Single users *can* submit jobs directly, but this is not the suggested way, and virtually no-one does
- Analists *can* use Ganga to submit jobs, but not too many still do
- Effectively, the vast majority of Analysis jobs come via Analysis Productions


---
layout: top-title
color: gray-light
align: c
title: migration
---

:: title ::

# DiracX in production

:: content ::

- LHCb migrated to DIRAC v9 + DiracX 0.0.1 (alpha versions) back in April
  - before data taking restarted
  - effectively, 1 week of downtime
    - largely, **not** because of DiracX: we "profited" also for making (too) many **optional** MySQL updates
      - this is what took **by far** most of the update time
  - reported in BiLD https://indico.cern.ch/event/1531451/
  - several fixes/updates followed
  - running in productions with alpha versions since
  - finally installed LHCbDIRAC v12.0 (on DIRAC v9.0) and lhcbdiracx v0.0.1 (on diracx v0.0.1)
    - also lhcbdiracx-web v0.0.1


---
layout: top-title
color: gray-light
align: c
title: functions
---

:: title ::

# What is DiracX used for in LHCb?

:: content ::

- JobStateUpdate is replaced by its DiracX "equivalent"
- Input and Output SBs are uploaded to s3

So, basically *everything* that DiracX can do at the moment

But also:
- interfacing with IaM (of course) to get user tokens
- we are starting to create user-facing web apps


---
layout: top-title
color: gray-light
align: c
title: IT
---

:: title ::

# Standing on the shoulders

:: content ::

CERN IT provides all needed services:

- MySQL 8.4 [on-demand](https://dbod-user-guide.web.cern.ch/)
- [IaM](https://lhcb-auth.cern.ch/)
- [Opensearch](https://opensearch.docs.cern.ch/)
- [Openshift](https://paas.docs.cern.ch) for hosting k8 projects
- [Object storage](https://clouddocs.web.cern.ch/object_store/index.html) compatible with S3, built upon Ceph
- [Grafana instance](https://monit.docs.cern.ch/grafana/description/) 
- OpenTelemetry (full support in progress)

Each of the above services come its with own monitoring (and sometimes we have look at it)


---
layout: top-title
color: gray-light
align: c
title: openshift
---

:: title ::

# OpenShift deployment

:: content ::

![openshift](/public/images/oc.png)


---
layout: top-title
color: gray-light
align: c
title: openshift-dev
---

:: title ::

# OpenShift deployment/2

:: content ::

![openshift](/public/images/oc_dev.png)

---
layout: top-title
color: gray-light
align: c
title: LHCbDiracXWeb
---

:: title ::

# lhcbdiracx-web

:: content ::

- Two new applications developed for lhcbdiracx-web.
- A bookkeeping application: a replacement for the old bookkeeping application with filtering capability. Work in Progress!
  - Search bookkeeping datasets by path elements
  - Browse results in a table or tree
  - To be extended with more features when backend performance stabilises

- A "storage report" application: a visualisation tool for LHCb storage. (also WIP!)


---
layout: top-title
color: gray-light
align: c
title: monitoring
---

:: title ::

# monitoring

:: content ::

![openshift](/public/images/monitoring.png)



---
layout: top-title
color: gray-light
align: c
title: OTEL
---

:: title ::

# infrastructure monitoring via OpenTelemetry

:: content ::

![otel](/public/images/otel_1.png)


---
layout: top-title
color: gray-light
align: c
title: OTEL2
---

:: title ::

# infrastructure monitoring via OpenTelemetry/2

:: content ::

![otel](/public/images/otel_2.png)



---
layout: top-title-two-cols
color: gray-light
align: c-lm-lm
title: CI
---

:: title ::

# Creating releases

:: left :: 

## LHCbDirac+X

1. Tag LHCbDIRACCommon (basically never needed)
2. If there is a new diracx tag renovate bumps the dependency in lhcbdiracx
3. Tag lhcbdiracx
4. lhcbdiracx's GitLab CI automatically make as commit to LHCbDIRAC and a MR to lhcbdiracx-charts
5. Merge in lhcbdiracx-charts -> automatically deploys lhcbdiracx to prod
6. Usual deployment for LHCbDIRAC legacy stuff

:: right ::

## LHCbDirac(+X)Web

1. If there is a new diracx-web tag renovate bumps the dependency in lhcbdiracx-web
2. Tag web
3. lhcbdirac-web's GitLab CI automatically make a MR to lhcbdiracx-charts


---
layout: top-title-two-cols
align: cm-cm-lm
color: orange-light
columns: is-4
title: summary
--- 
:: title ::

# Summary

:: left :: 

![LHCb](/public/images/LHCb.png)


:: right ::

- We have been running (LHCb)DiracX(-Web) in production since April
- It works!
  - but we relied heavily on the internal knowledge
- LHCb have always been and will keep being a Dirac(X) supporter


---
layout: credits
color: navy
loop: true
speed: 1.0
title: credits/people
---


<div class="grid text-size-4 grid-cols-3 w-3/4 gap-y-10 auto-rows-min ml-auto mr-auto">
    <div class="grid-item text-center mr-0- col-span-3">
        <strong>People</strong><br> 
    </div>
    <div class="grid-item text-right mr-4 col-span-1">
        <strong>Current Developers, maintainers, supporters</strong>
    </div>
    <div class="grid-item col-span-2">
        Chris Burr <i>CERN</i><br/>
        Christophe Haen <i>CERN</i><br/>
        Alexandre Boyer <i>CERN</i><br/>
        Ryunosuke O'Neil (Wada) <i>CERN</i><br/>
        Federico Stagni <i>CERN</i><br/>
        Vladimir Romanovskiy <i>Cincinnati</i>
    </div>
</div>

&nbsp;
&nbsp;
&nbsp;

<div class="grid-item col-span-3 text-center mt-180px mb-auto font-size-1.5rem">
    <strong>Questions?</strong>
</div>
