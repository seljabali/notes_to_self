## Application
When networking requests come in it is converted to an `ApplicationCall` and goes through a pipeline which is owned by the Application. The pipeline consists interceptor(s), providing routing, compression, etc. 

## Module
A user-defined function receiving the Application class that is in charge of configuring the server pipeline, install features, registering routes, handling requests, etc.

## Feature
A feature is a singleton (usually a companion object) that you can install and configure for a pipeline.

## Application Engines
Ktor can run any servlet container with 3.0+ support including Google Cloud.
### CIO
Coroutines I/O http server. JetBrains made.
### Jetty
Eclipse version.
### Netty
Framework, not so much a server. Path of least resistance.
### Tomcat
Is Tomcode.
