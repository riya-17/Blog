---
layout: post
title: Pbench - one ring to rule them all
---

![_config.yml]({{ site.baseurl }}/images/giphy.gif)

Hello world,

Pbench is a short of "Performance bench", is a comprehensive framework that assist engineers with their benchmarking and performance analysis.

The framework in short strives to make the life of performance engineer more efficient and comprehensive. The most products mowadays are distributed systems and our team members run the same or similar benchmarks with their own wrappers in order to gather data. This process lead to incomplete or inconsistent data collection depending on who ran it. We found it difficult to compare data sets, or found incomplete data depending on who ran what. So, we worked to come up with a framework that captured the best practices across the team.

<h5>The Framework allows user to:</h5>

- Collect data from one or more than one systems <br>
- Indexes and verifies it <br>
- Helps to visually analyse it <br>

<br>

<h3>Motivation</h3>
The thought to improve our ability to collect and visualize performance analysis data and automate our workloads. The key was creating a tool which would be convenient, user-friendly, and powerful. In performance work, you may need to use quite a lot of tools to understand the problem, as well as run workloads with many permutations. Pbench sought to make this much more accessible by providing common commands to use these tools and benchmarks. Once the user knew a couple of simple commands for pbench, they could run dozens of tools and workloads.

<h5>With this background, the pbench framework is being developed with the following goals in mind:</h5>

- Provide easy access to benchmarking & performance tools on Linux systems
- Standardize the collection of telemetry and configuration information
- Automate benchmark execution and collection of results
- Output effective visualization for analysis (locally, as well as on a remote pbench server)
- Allow for ingestion into Elasticsearch and advanced data analysis through easy-to-use dashboards

<br>

<h3>The Framework consists of the following subsystems:</h3><br>

![_config.yml]({{ site.baseurl }}/images/Pbench-component.png)

**Pbench-agent**: is a collection agent and benchmark wrapper, or harness, responsible for providing commands for running benchmarks across one or more systems under test, while properly collecting the configuration of those systems, their logs, and specified telemetry from various tools (sar, vmstat, perf, etc.), and performing some level of normalization of the various pieces of data collected. The pbench-agent must be installed on the set of systems the user would like data collected from during a benchmark run.<br>

**Pbench-server**: runs on a remote system and is responsible for archiving the result tarballs, indexing them into an Elasticsearch instance, and unpacking them for visualization.<br>

**Dashboard**: is the front-end to the results data captured through the pbench agent and is integrated with other visualization tools such as Kibana or Grafana.

<br>

<h3>What are some of many benchmarks offered by Pbench?</h3><br>

**Pbench-user-benchmark** - This script helps us to run a custom benchmark.  It collects data of the tools that are listed in the group, the group can be the default group or user created group. <br>
**Pbench-fio** - It is a workload generator that can be used for both benchmark and stress/hardware verification. It was created to automate fio tests, including calculations of statistics for throughputs and latency. <br>
**Pbench-uperf** - helps us in network performance testing. It helps us to know the capacity of your entire network infrastructure to support the desired level of traffic induced by distributed storage, using multiple network connections in parallel. 

<br>

<h3>WorkFlow</h3><br>

![_config.yml]({{ site.baseurl }}/images/Pbench_workflow.png)

Agent acts as a collection spot of data. It collects the data and send to server with the help of `pbench-move-results` command. Server acts as a collector of data. It helps to verify the tarballs by checking whether the data that is collected is valid and error free. It then indexes the data and send to elasticsearch. Elasticsearch mapped data is then fetched by the Dashboard and Kibana for Visualization where we can compare or visualize our data with the help of tables or graphs easily.

<br>

<h3>Future work</h3><br>

**Agent**:
- Conversion to all Python3 Scripts (removing remaining complicated bash scripts) <br>
- Having a unified platform for running tools <br>

**Server**
- Conversion to all Python3 Scripts (removing remaining bash and perl scripts) <br>
- Addition of new features (deletion of unpacked tarballs if time exceeds 30 days) <br>
- Introduction of User notion <br>

**Dasboard**
- 

<br>

<h3>For Your Love and Contribution</h3><br>
GitHub Repo: - [Pbench GitHub Repository](https://github.com/distributed-system-analysis/pbench)
