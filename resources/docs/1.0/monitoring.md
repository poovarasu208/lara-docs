# Monitoring (New Relic)

- [New Relic](#monitoring-new-relic)
- [Installation](#installation)
- [Features](#features)
- [Application Monitoring](#application-monitoring)

<a name="monitoring-new-relic"></a>
## New Relic
[`website`](https://newrelic.com/)

New Relic is an Application Performance Management (APM) used by teams for application monitoring to maximize the productivity and minimize the downtime by looking at different stats responsible for overall application performance.

<a name="installation"></a>
## Installation
[`Documentation`](https://docs.newrelic.com/docs/agents/php-agent/installation/php-agent-installation-overview)

- Ensure your system meets the agent's requirements, including appropriate system permissions.

- If you do not already have a New Relic account, create one.

- From your New Relic Account settings, copy your license key information.

- Install the agent package or tar archive on your system.

- Change the default application name to a meaningful name.

- Optional: Change other agent configuration settings to further customize your installation.

- Restart your web server (Apache, Nginx, PHP-FPM, etc.).

<a name="features"></a>
## Features
### Infrastructure Health
Infrastructure collects and displays health metrics such as CPU, Load, Memory, etc. at the host level, as well as individual Process, Network and Storage level. Additionally, apply filters based on tags, metadata and custom attributes that allows to slice-and-dice into a subset of the infrastructure and view metrics for those.

### Dashboards and Alerting
Use tags and custom metadata to scale critical alerts dynamically as hosts change. Create Alerts based on host attributes and EC2 tags that dynamically get associated with hosts.

### Up-to-date Inventory
Full search of all your hosts that makes it easy to find vulnerable packages—or anything else—in seconds.

### Full Stack Monitoring
When combining APM and Infrastructure monitoring with the data-analysis capabilities of Insights, we can easily track changes in our infrastructure that could affect our applications.

### Cloud Native
Optimize cloud infrastructure performance and efficiency to deliver the best experience for customers.

### New Relic Integrations
[`website`](https://docs.newrelic.com/docs/integrations/new-relic-integrations/getting-started/introduction-infrastructure-integrations)

New Relic Infrastructure integrations send data from popular services to New Relic products, including Infrastructure, Insights, and Alerts. After installing and activating an integration, we can:

- Filter and analyze the metrics and configuration data in New Relic Infrastructure.

- Query data and create custom dashboards in New Relic Insights.

- Create alert conditions to monitor problems with our service's performance in New Relic Alerts.

Available integrations includes: [`Amazon Web Services (AWS) cloud-based integrations`](https://docs.newrelic.com/docs/integrations/amazon-integrations/aws-integrations-list),[`Microsoft Azure cloud-based integrations`](https://docs.newrelic.com/docs/integrations/microsoft-azure-integrations/azure-integrations-list),
[`Google Cloud Platform (GCP) cloud-based integrations`](https://docs.newrelic.com/docs/integrations/google-cloud-platform-integrations/gcp-integrations-list),[`On-host integrations built by New Relic`](https://docs.newrelic.com/docs/integrations/host-integrations/host-integrations-list),
[`On-host integrations built by the open-source community`](https://docs.newrelic.com/docs/integrations/host-integrations/open-source-host-integrations-list),[`Custom On-host integrations`](https://docs.newrelic.com/docs/integrations/integrations-sdk/getting-started/introduction-infrastructure-integrations-sdk)
## Application Monitoring
[`Documentation`](https://docs.newrelic.com/docs/apm/applications-menu)
It is a process which makes sure that the specific application or software is running the way it is designed for
### Overview
[`website`](https://docs.newrelic.com/docs/apm/applications-menu/monitoring/apm-overview-page)

New Relic APM's Overview page provides general information about the selected app, including web transactions and non-web transactions, Apdex score, CPU usage, throughput (requests per minute or rpm), transaction times, error rate, recent events, and hosts.

![image](/images/new_relic_overview.png)

### Transactions
[`website`](https://docs.newrelic.com/docs/apm/transactions/intro-transactions/transactions-new-relic-apm)

At New Relic, a transaction is defined as one logical unit of work in a software application. It will often refer to a web transaction, which represents activity that happens from when the application receives a web request to when the response is sent.

![image](/images/new_relic_transactions.png)



 
 
                                                           
                                                           
                                                           
                                                           
                                                           
                                                           
