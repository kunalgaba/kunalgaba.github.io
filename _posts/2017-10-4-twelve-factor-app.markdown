---
layout: post
title:  "12 factor App principles"
date:   2017-10-3 16:02:15
categories: Design
---
# 12 factor App principles

There are many articles on the web from where you can read about 12 factor app principles or methodology. The 12 factor app methodology is used for building and designing cloud-native apps.

I have tried to summarise the 12 factor app principles here on this page in a concise way.This will give you a simple and quick view of all 12 principles in one view just like a cheatsheet.


| Factor | Principle                   |       What it means     | More Info  |
|--------| ----------------------------|-------------| --------------|
|Code| One codebase tracked in revision control, many deploys | Every app code should be versioned and should have it's own source code. No sharing of code between multiple apps. |  <https://12factor.net/codebase> |
|Dependencies|Explicitly declare and isolate dependencies | Do not assume dependencies instead declare them explicitly and use a mechanism to isolate them at runtime  |  <https://12factor.net/dependencies> |
|Config|Store config in the environment | Strictly separate config from code. Store your config in env variables for different run time environments. |  <https://12factor.net/config> |
|Backing Services|Treat backing services as attached resources| All backend services whether 3rd party or not should be considered as resources. There should be no impact on the app if the implementation of the backing services is swapped with something new. The resources can be attached and detached at will without any impact to the app. | <https://12factor.net/backing-services> |
|Build, release, run|Strictly separate build and run stages|Build, run and deploy should be separate stages and should not overlap. |<https://12factor.net/build-release-run>|
|Processes|Execute the app as one or more stateless processes|Build stateless processes and do not rely on local caches like memory and filesystem. All state data should be persisted in a backend datastore so that any process can respond to future incoming requests.  |<https://12factor.net/processes>
|Port binding|Export services via port binding|Build self contained apps by declaring a dependency on a server library like webserver and bind your service to a port. Do not assume the webserver injection at run time.|<https://12factor.net/port-binding>
|Concurrency|Scale out via the process model|Architect your app to handle diverse workloads by assigning each type of work as a process type. The scaling and concurrency becomes simple and reliable due to share nothing nature of a 12 factor app.|<https://12factor.net/concurrency>
|Disposability|Maximize robustness with fast startup and graceful shutdown|Apps can be started or stopped at a moment’s notice. Minimise startup time and implement graceful shutdowns for elasticity.|<https://12factor.net/disposability>
|Dev/prod parity|Keep development, staging, and production as similar as possible|Mimic prod env in dev and follow continuous delivery.|<https://12factor.net/dev-prod-parity>
|Logs|Treat logs as event streams|Do not write logs in a file or in any other storage. Instead log events should be written to standard output stream for collation later by execution environment. |<https://12factor.net/logs>
|Admin processes|Run admin/management tasks as one-off processes|Run one-off process in identical environment and should run against a release.|<https://12factor.net/admin-processes>



