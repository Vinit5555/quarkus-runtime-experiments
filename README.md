# Quarkus Runtime-Aware Container Exploration

This repository contains a Quarkus-based Java microservice designed as a controlled testbed for analysing runtime behaviour of enterprise Java applications in containerised environments.
The service is intentionally minimal in business logic and structured to enable focused investigation of runtime characteristics under varying container resource constraints.



## Motivation

Modern Java workloads are widely deployed in Kubernetes and other container orchestration platforms. While container autotuning tools optimise CPU and memory allocations based primarily on steady-state metrics, JVM-based applications exhibit behaviours such as:

Startup latency

Warm-up effects (JIT compilation behaviour)

Dynamic memory adaptation

These characteristics may not be fully captured by traditional steady-state optimisation strategies.

This repository serves as a foundation for exploring whether runtime-specific characteristics of JVM-based workloads influence container optimisation effectiveness.



## Research Direction


This project aims to investigate:

-Startup time behaviour of JVM-based services in constrained containers

-Memory footprint characteristics under limited resource conditions

-CPU allocation sensitivity for REST-based microservices

-Whether steady-state metric-based tuning sufficiently captures runtime-specific behaviour

The longer-term objective is to explore how container resource optimisation strategies might be improved by incorporating awareness of runtime startup and warm-up characteristics.




## Technologies Used

Java

Quarkus

Maven

Docker

RESTful APIs



## Project Structure

- `src/` — Java source code for the Quarkus microservice
- `pom.xml` — Maven build configuration
- `src/main/docker/` — Dockerfiles for container deployment
- `mvnw` and `.mvn/` — Maven wrapper for reproducible builds



## Build and Run

### Build in JVM Mode

```bash
./mvnw clean package

## Run in Development Mode
./mvnw quarkus:dev

##Build Docker Image
docker build -f src/main/docker/Dockerfile.jvm -t quarkus-service .

##Run Container with Resource Constraints
docker run -m 512m --cpus=1 -p 8080:8080 quarkus-service

##Purpose

This repository is not intended to represent a production system.
It is designed as a focused runtime-behaviour exploration environment to support investigation into container optimisation strategies for enterprise Java workloads.



