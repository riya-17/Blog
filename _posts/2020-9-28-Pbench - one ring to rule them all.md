---
layout: post
title: Pbench - one ring to rule them all
---

![_config.yml]({{ site.baseurl }}/images/giphy.gif)

---
layout: post
title: My Open Source Experience!
---

![_config.yml]({{ site.baseurl }}/images/open-source.png)

Hello world,

Pbench is a short of "Performance bench", is a comprehensive framework that assist engineers with their benchmarking and performance analysis.

The framework in short strives to make the life of performance engineer more efficient and comprehensive. The most products mowadays are distributed systems and our team members run the same or similar benchmarks with their own wrappers in order to gather data. This process lead to incomplete or inconsistent data collection depending on who ran it. We found it difficult to compare data sets, or found incomplete data depending on who ran what. So, we worked to come up with a framework that captured the best practices across the team.

The Framework allows user to:
\* Collect data from one or more than one systems
\* Indexes and verifies it
\* Helps to visually analyse it 

Motivation
The thought to improve our ability to collect and visualize performance analysis data and automate our workloads. The key was creating a tool which would be convenient, user-friendly, and powerful. In performance work, you may need to use quite a lot of tools to understand the problem, as well as run workloads with many permutations. Pbench sought to make this much more accessible by providing common commands to use these tools and benchmarks. Once the user knew a couple of simple commands for pbench, they could run dozens of tools and workloads.

With this background, the pbench framework is being developed with the following goals in mind:

\* Provide easy access to benchmarking & performance tools on Linux systems
\* Standardize the collection of telemetry and configuration information
\* Automate benchmark execution and collection of results
\* Output effective visualization for analysis (locally, as well as on a remote pbench server)
\* Allow for ingestion into Elasticsearch and advanced data analysis through easy-to-use dashboards

The Framework consists of the following subsystems:
pbench-agent: is a collection agent and benchmark wrapper, or harness, responsible for providing commands for running benchmarks across one or more systems under test, while properly collecting the configuration of those systems, their logs, and specified telemetry from various tools (sar, vmstat, perf, etc.), and performing some level of normalization of the various pieces of data collected. The pbench-agent must be installed on the set of systems the user would like data collected from during a benchmark run.

Pbench-server: runs on a remote system and is responsible for archiving the result tarballs, indexing them into an Elasticsearch instance, and unpacking them for visualization.

Dashboard: is the front-end to the results data captured through the pbench agent and is integrated with other visualization tools such as Kibana or Grafana.

What are some of many benchmarks offered by Pbench?
Pbench-user-benchmark - This script helps us to run a custom benchmark.  It collects data of the tools that are listed in the group, the group can be the default group or user created group.
Pbench-fio - It is a workload generator that can be used for both benchmark and stress/hardware verification. It was created to automate fio tests, including calculations of statistics for throughputs and latency. 
Pbench-uperf - helps us in network performance testing. It helps us to know the capacity of your entire network infrastructure to support the desired level of traffic induced by distributed storage, using multiple network connections in parallel.


Usage
Using the pbench framework is a breeze. Start off by installing the pbench-agent on all the systems under test - there are Ansible scripts in the repo to facilitate pbench-agent installation. Then, execute the following protocol in-order to run a benchmark:

\- Register a set of tools on all systems under test
      This step is usually performed from just one host as the tool registration utility has the capability to register tools on remote hosts
\- Run the benchmark using the pbench benchmark wrapper scripts; the pbench benchmark wrapper scripts ensure the following:
      automatic installation of benchmark
      detailed results for a matrix of benchmark iterations
      multi-sampling of each iteration for average and standard deviation
      tool execution during measurement periods (for the tools that were registered in the previous step)
      support for multi-system synchronized execution
      provide result metrics beyond “throughput”, and integrate tool data to derive efficiency metrics (Gbps/CPU, IOPS/CPU, etc.)
\- (optional) Move the results to the remote pbench server if installed
\- Visualize the results either locally using the web server JS and CSS file components or on the dashboard of the remote server



<h3>The Challenge</h3>

GSoC 
