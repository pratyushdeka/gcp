Cloud Run
- A managed compute platform that can run stateless containers via web requests or Pub/Sub events
- Serverless, removing the need for infrastructure management (focus should be on development)
- Built on Knative, an open API and runtime environment built on Kubernetes
- Fast - can automatically scale up and down from zero almost instantaneously, charging only for the resources used

Cloud Run developer workflow
- Write your application - the app should starts a server that listens for web requests
- Build and package the app into a container image
- The container image is pushed to artifact repository where Cloud will deploy it
Cloud Run then starts your container on demand to handle requests, and ensures that all incoming requests are handled by dynamically adding and removing containers

Container-based workflow gives you
- transparency
- flexibility

With Cloud Run you can use a container-based workflow as well as s source-based workflow. The source-based approach will deploy source code instead of a container image. Cloud Run then builds the source and packages the application into a container image. Cloud Run does this using Buildpacks - an open source project. Cloud Run handles HTTPS serving for you.

Pricing model
- Unique
- Only pay for the system resources you use while a container is handling web requests, with a granularity of 100ms, and when it’s starting or shutting down
- Additionally, there is a small fee for every one million requests you serve
- The price of container time increases with CPU and memory. A container with more vCPU and memory is more expensive

Cloud Run Functions
- A lightweight, event-based, asynchronous compute solution
- Allows you to create small, single-purpose functions that respond to cloud events, without the need to manage a server or a runtime environment
- Construct application workflows from individual business logic tasks and connect and extend cloud services
- Billed to the nearest 100 milliseconds, but only while your code is running
- Supports writing source code in a number of programming languages
- Events from Cloud Storage and Pub/Sub can trigger Cloud Run functions asynchronously, or you can use HTTP invocation for synchronous execution