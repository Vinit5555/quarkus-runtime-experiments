# Quarkus Runtime-Aware Container Exploration

This repository contains a Quarkus-based Java microservice designed as a
controlled testbed for analysing runtime behaviour of enterprise Java
applications in containerized environments.

The project is intentionally minimal in business logic and structured
to allow focused investigation of runtime characteristics under
different container resource constraints.



## Motivation

Modern Java workloads are increasingly deployed in Kubernetes and other
container orchestration platforms. While container autotuning tools
optimise CPU and memory allocations based on steady-state metrics,
Java runtimes exhibit behaviour such as startup latency, warm-up
effects, and dynamic memory adaptation that may not be fully captured
by traditional tuning strategies.

This repository serves as a foundation for exploring whether runtime-
specific characteristics of JVM-based workloads influence container
optimisation effectiveness.



## Research Direction

This project aims to investigate:

- Startup time behaviour of JVM-based services in constrained containers
- Memory footprint characteristics under limited resource conditions
- CPU allocation sensitivity for REST-based microservices
- Whether steady-state metric-based tuning sufficiently captures
  runtime-specific behaviour

The long-term objective is to explore how container resource
optimisation strategies might be improved by incorporating awareness
of runtime startup and warm-up characteristics.



## Technologies Used

- Java
- Quarkus
- Maven
- Docker
- RESTful APIs



## Project Structure

- `src/` — Java source code for the Quarkus microservice
- `pom.xml` — Maven build configuration
- `src/main/docker/` — Dockerfiles for container deployment
- `mvnw` and `.mvn/` — Maven wrapper for reproducible builds



## Build and Run

### Build in JVM Mode

```bash
./mvnw clean package
