# Frequently Asked Questions

### Am I required to have the Application Insights Profiler enabled in order to see the Optimization Insights?

Yes. The Application Insights (App Insights) Profiler collects profiling data used as an input to generate the Optimization Insights. We recommend using the App Insights Profiler, since it helps you diagnose performance issues in your application. 

[Learn more about how to enable the App Insights Profiler](https://docs.microsoft.com/en-us/azure/azure-monitor/app/profiler-overview).

### How does Optimization Insights work under the hood?

Optimization Insights uses Microsoft’s internal profiling data and Artificial Intelligence (AI) algorithms to detect performance bugs.

1. Microsoft’s internal profiler collects random samples of stack traces from Microsoft's own services and applications running on Azure, which amount to thousands of traces collected daily. 
1. Microsoft then leverages this data to build detection techniques that can:
   - Distinguish between what is and isn’t a client’s application code in a trace.
   - Determine when a function is being used inefficiently.
   - Base techniques on best practices learned from thousands of .NET application traces that are:
       - Internal to Microsoft.
       - Currently in production.

### What's the difference between the App Insights Profiler and Optimization Insights?

Microsoft's App Insights Profiler and Optimization Insights work together to provide a holistic approach to performance issue detection.

#### App Insights Profiler

Application Insights focuses on tracing specific requests, down to the millisecond. It provides an excellent "big picture" view of issues within your application and general best practices to address them.

#### Optimization Insights

Optimization Insights draws from Application Insights, requiring you to have your profiler enabled in order to take advantage of Optimization Insights. On top of the big picture provided by Application Insights, Optimization Insights:

- Displays aggregated data gathered over time.
  - By default, data samples are collected at least once an hour, with only one trace per role name per hour.
- Connects data with the methods and functions in your application code.
- Narrows down on the culprit for bottle-necking within the code.

### How should I read the Memory Issue and CPU numbers?

For Memory Issue Details, the number is just a percentage of all allocations made within the trace. For example, if an issue takes 24%, that means you spent 24% of all your allocations within that call. 

For CPU, the percentage is based on the number of CPUs in your machine (4 core, 8 core, etc.) and the trace time. For example, it’s a percentage of the total wall clock time of the trace.

We also include the actual allocation sizes (in bytes) and a breakdown of the allocated types made within the call.

### Does enabling Optimization Insights result in additional overhead?

Since Optimization Insights works entirely offline using the profiles uploaded by the App Insights Profiler, there's no extra overhead.

### How often should I review the Optimization Insights?

We recommend routinely reviewing Optimization Insights. New performance issues can be detected based on:

- The application load.
- How the application is exercised by the users. 

Many users check which Optimization Insights are generated when they run their load tests.

### How do I go about prioritizing a particular recommendation provided by Optimization Insights relative to other recommendations as well as other tasks that developers need to work on?

We recommend that you prioritize issue remediation based on the values shown in the Count and Impact columns. 

### Will I incur any additional costs for testing Optimization Insights in the private preview?

Optimization Insights are included at no additional costs for App Insights Profiler customers. However, although minor, there are indirect costs associated with running the App Insights Profiler. First, the Profiler’s metadata is sent to your App Insights resource, which Application Insights charges for. In the basic pricing plan, your application can send a certain allowance of data each month free of charge. Second, the Profiler uploads profiles to the same region where your Application Insights was created. Therefore, if your application is running in a different region than that of your App Insights resource, we have to send profiler data across different regions. As a result, although very small, you will incur networking costs. 

### Will Optimization Insights continue to be free once it becomes generally available?
We will provide more information on this topic once the product becomes generally available in 2022.

### What does the roadmap for Optimization Insights look like?
The roadmap for Optimization Insights is not currently public. However, we are continuously working on making the product better and would love to hear your feedback! If you have any suggestions or questions, please send us an email at **opt_insights@microsoft.com**.

### How long does it take for the Optimization Insights to appear in the UI after the profiler data is collected? 
The Optimization Insights are shown in near real time as the profiler data is ingested and analyzed.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
**[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general)**.
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
