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

# The LHCb case -- the helm chart

:: content ::

show lhcbdiracx chart


---
layout: top-title
color: gray-light
align: c
title: client
---

:: title ::

# The LHCb case -- the client

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

# The LHCb case -- lhcbdiracx

:: content ::


---
layout: top-title
color: gray-light
align: c
title: LHCbDiracXWeb
---

:: title ::

# The LHCb case -- lhcbdiracx-web

:: content ::


---
layout: top-title
color: gray-light
align: c
title: monitoring
---

:: title ::

# The LHCb case -- monitoring

:: content ::


---
layout: top-title
color: gray-light
align: c
title: OTEL
---

:: title ::

# The LHCb case -- infrastructure monitoring via OpenTelemetry

:: content ::


---
layout: top-title
color: gray-light
align: c
title: lhcbdiracx
---

:: title ::

# lhcbdiracx

:: content :: 



---
layout: top-title
color: gray-light
align: c
title: lhcbdiracx-web
---

:: title ::

# lhcbdiracx-web

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
        Chris Burr <i>CERN, LHCb</i><br/>
        Christophe Haen <i>CERN, LHCb</i><br/>
        Alexandre Boyer <i>CERN, LHCb</i><br/>
        Ryunosuke O'Neil <i>CERN, LHCb</i><br/>
        Federico Stagni <i>CERN, LHCb</i>
    </div>
</div>

&nbsp;
&nbsp;
&nbsp;

<div class="grid-item col-span-3 text-center mt-180px mb-auto font-size-1.5rem">
    <strong>Questions?</strong>
</div>

---
layout: section
color: cyan-light
title: Backup
---

# Backup
