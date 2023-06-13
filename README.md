# Buildkite Example Pipeline for Concurrency Gates

This repository contains an example [Buildkite](https://buildkite.com/) pipeline for using [Concurrency](https://buildkite.com/blog/concurrency-gates) [Gates](https://buildkite.com/docs/pipelines/controlling-concurrency#concurrency-and-parallelism).

To see this in action, manually start 2 builds using this pipeline.
- Run the first build setting the following environment variable; `PRE_GATE_SLEEP=60`
- Run the second build without setting any environment variables.

Notice that even though the second build reaches the concurrency gate first, it waits for the first build to complete it's steps in the concurrency gate.  

This is because Concurrency Groups guarantee that jobs will be run in the order that they were created in.
