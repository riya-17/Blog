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

Performance Engineers often find themselves building distributed system solutions to run and publish benchmark numbers, the main issue that arises is inconsistent data collection. Outdated industry practices and hard-to-use tools to collect data keep people from making the most of their data. What is collected is often incomplete, slow to update, and cumbersome to analyze. This is where Pbench comes to the rescue.

What is the issue:
 Performance Engineers often find themselves building distributed system solutions to run and publish benchmark numbers, the main issue that arises is inconsistent data collection. Outdated industry practices and hard-to-use tools to collect data keep people from making the most of their data. What is collected is often incomplete, slow to update, and cumbersome to analyze. This is where Pbench comes to the rescue.

Previous Solutions:
As we  know, most of the industrial products are distributed systems and our team members were running the same or similar benchmarks with their own wrappers in order to gather data. This process leads to incomplete or inconsistent data collection depending on who ran it.  So we worked on a framework that helped us establish the best practices in order to collect similar kinds of data for a benchmark. That framework is Pbench. 

Our solution:
Pbench is a harness that allows data collection from a variety of tools while running a benchmark. It provides you the ability to capture configuration and tool data. We build a benchmarking tool that works in all environments such as bare metal, on Prem cloud, public clouds, and makes it much easier to collect the required configuration along with tools data at scale. It helps maintain consistency of data during the runs and helps to analyze the collected data to facilitate comparisons by a dashboard.

Other products: 
With distributed system support
Periscope
Without distributed system support



How Pbench is useful:
Enhanced performance metric. Pbench is useful in the collection of consistent data and only the data you want to collect. It gives you the choice of data you want to collect, you just need to register the tools whose data you need to collect. No, extra or useless data. It gives you ease to visualize your data. Also, you can collect data from any number of machines as you require. You will just need to install pbench-agent in all those machines whose data you need to collect, collect data, send data to a single server.



<h3>The Challenge</h3>

GSoC 
