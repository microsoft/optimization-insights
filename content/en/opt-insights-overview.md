# Optimization Insights service (private preview)

Performance bugs are consistently difficult to detect in today’s online services, since they:

- Don’t cause system failure. 
- Are dependent on user input.
- In some cases, only manifest with specific inputs.
- Can be introduced by anyone, even experts.
- Propagate easily by code reuse.  

To detect performance bugs and provide insights in your application, Optimization Insights relies on an AI-model. This AI-based service identifies and removes CPU and memory bottlenecks by:

- Analyzing the runtime behavior of your application.
- Comparing the behavior analysis to performance engineering best practices.

Optimization Insights bases its analysis and comparison on lessons learned from thousands of applications profiled internally at Microsoft.

## Pre-requisites

Before you can use Optimization Insights on your Azure resource, [enable the Application Insights Profiler](https://docs.microsoft.com/en-us/azure/azure-monitor/app/profiler-overview).

## Navigate to Optimization Insights

If you are using Application Insights Profiler to monitor your Azure resources' performance health, you may have noticed the new **Optimization Insights (preview)** tab from your resource's profiler page. Navigate to that tab to view the insights we've identified in your application over the last 24 hours.

From your Azure Application Insights resource overview page, select **Optimization Insights (preview)** under **Investigate** in the left navigation pane.

![Screenshot of Optimization Insights located in the left side navigation pane](./extras/overview-images/nav-pane.png)

You can sort the insights based on:

- Extra memory or CPU usage (impact).
- Issue frequency within a specific time period (count).
- Role, if your service has multiple roles.

![Screenshot pointing out where you can filter the Optimization Insights](./extras/overview-images/opt-insights-1.png)

Select each insight to view:

- Detailed description of the performance bug insight.
- Recommendations on fixing the performance issue.

![Screenshot showing the description and recommendations associated with one of the insights](./extras/overview-images/opt-insights-2.png)

Access the full call stack surrounding the performance issue via the call stack button.

![Screenshot showing where you can select "Call Stack"](./extras/overview-images/opt-insights-3.png)

![Screenshot showing the Call Stack results](./extras/overview-images/opt-insights-4.png)

## Difference between Application Insights and Optimization Insights

Microsoft's Application Insights Profiler and Optimization Insights work together to provide a holistic approach to performance issue detection.

### Application Insights

Application Insights focuses on tracing specific requests, down to the millisecond. It provides an excellent "big picture" view of issues within your application and general best practices to address them.

### Optimization Insights

Optimization Insights draws from Application Insights, requiring you to have your profiler enabled in order to take advantage of Optimization Insights. On top of the big picture provided by Application Insights, Optimization Insights:

- Displays aggregated data gathered over time.
- Connects data with the methods and functions in your application code.
- Narrows down on the culprit for bottle-necking within the code.

## Next Steps

- For more information, review our [FAQ page](faq.md).
- If you have any further questions, email the [Optimization Insights team](mailto:opt_insights@microsoft.com).