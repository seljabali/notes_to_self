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

## Application Environment
Created by Application Engine.
- `application.conf` is config files for server
- Host, port, modules
- Using a lang: hokan ~ json.

## Application
When networking requests come in it is converted to an `ApplicationCall` and goes through a pipeline which is owned by the Application. The pipeline consists interceptor(s), providing routing, compression, etc. 
- Subclasses Pipeline.
- It is a pipeline.
- Has 5 Phases:
  1. Setup
  2. Moniotor
  3. Feature
  4. Call
  5. Fallback

## Module
A user-defined function receiving the Application class that is in charge of configuring the server pipeline, install features, registering routes, handling requests, etc.
- First thing that it's called.

## Pipelines
- A series of events.

## Phases
- Have Interceptors 
- Listening async
- Pass to the next interceptors.

## Features
A feature is a singleton (usually a companion object) that you can install and configure for a pipeline.
- Example: DefaultHeaders (adds server & timestamp)
```kotlin
fun Applicaiton.module() {
  install(DefaultHeaders)
}
```
- Example: Routes
