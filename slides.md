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

- JobStateUpdate
- ISBs
- lhcbdiracx-web




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
- OTEL

Each of the above services come its with own monitoring (and sometimes we have look at it)


---
layout: top-title
color: gray-light
align: c
title: chart
---

:: title ::

# The helm chart

:: content ::

show lhcbdiracx chart


---
layout: top-title
color: gray-light
align: c
title: client
---

:: title ::

# The client

:: content ::

how the client is installed and deployed on CVMFS

including which env variables?


---
layout: top-title
color: gray-light
align: c
title: LHCbDiracX
---

:: title ::

# lhcbdiracx

:: content ::


---
layout: top-title
color: gray-light
align: c
title: LHCbDiracXWeb
---

:: title ::

# lhcbdiracx-web

:: content ::


---
layout: top-title
color: gray-light
align: c
title: monitoring
---

:: title ::

# monitoring

:: content ::


---
layout: top-title
color: gray-light
align: c
title: OTEL
---

:: title ::

# infrastructure monitoring via OpenTelemetry

:: content ::


---
layout: top-title
color: gray-light
align: c
title: LHCbDIRACCommon
---

:: title ::

# LHCbDIRACCommon

:: content :: 


---
layout: top-title
color: gray-light
align: c
title: CI
---

:: title ::

# What we do in gitlab-CI

:: content :: 


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
