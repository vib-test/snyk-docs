# Integrations for Snyk AppRisk

## Overview

The Integrations page shows all active integrations, including any data automatically synced from your existing Snyk Organizations, and provides access to the Integration Hub.

{% hint style="warning" %}
Use the Snyk AppRisk Pro version to integrate third-party with SAST and Secret Detection tools.\
Snyk AppRisk Pro is currently available in Closed Beta. Please contact your salesperson if you are interested in Snyk AppRisk Pro.
{% endhint %}

The following supported Snyk data are automatically synced:

* Snyk Open Source
* Snyk Code
* Snyk IaC
* Snyk Container

Each connected integration enables you to:

* Pause data syncing
* Modify integration profiles and configurations
* Delete the integration
* Check when the integration was last synced and when the next sync is scheduled.

### Snyk AppRisk integrations ecosystem

You can refer to the table below to verify the availability and compatibility of all integrations for Snyk AppRisk. The integrations are categorized by type, listed by name, and indicated as available or not for both Snyk AppRisk Essentials and Snyk AppRisk Pro.

<table><thead><tr><th width="172">Integration type</th><th width="164">Integration name</th><th width="198">Snyk AppRisk Essentials</th><th>Snyk AppRisk Pro</th></tr></thead><tbody><tr><td>SCM</td><td><ul><li><a href="connect-an-scm-integration.md#github-setup-guide">GitHub</a></li><li><a href="connect-an-scm-integration.md#bitbucket-setup-guide">BitBucket</a></li><li><a href="connect-an-scm-integration.md#gitlab-setup-guide">GitLab</a></li><li><a href="connect-an-scm-integration.md#azure-devops-setup-guide">Azure DevOps</a></li></ul></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td></tr><tr><td>Dev portals and Service catalogs</td><td><ul><li><a href="application-context-for-scm-integrations.md">Backstage catalog</a></li><li><a href="connect-a-third-party-integration.md#servicenow-cmdb-setup-guide">ServiceNow CMDB</a></li></ul></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td></tr><tr><td>Risk management collaboration</td><td><ul><li><a href="connect-a-third-party-integration.md#jira-setup-guide">Jira</a></li><li><a href="../../../integrate-with-snyk/jira-and-slack-integrations/slack-integration.md">Slack</a></li><li>Email</li></ul></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td></tr><tr><td>AST</td><td><ul><li><a href="connect-a-third-party-integration.md#nightfall-setup-guide">NightFall</a></li><li><a href="connect-a-third-party-integration.md#gitguardian-setup-guide">GitGuardian</a></li></ul></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2716">✖️</span></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td></tr><tr><td>Runtime security and observability</td><td><ul><li><a href="snyk-runtime-sensor.md">Snyk runtime sensor</a></li><li><a href="connect-a-third-party-integration.md#sysdig-setup-guide">Sysdig</a></li><li><a href="connect-a-third-party-integration.md#dynatrace-setup-guide">Dynatrace</a></li></ul></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2716">✖️</span></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2714">✔️</span></td></tr></tbody></table>

## Using the Integration Hub

Use the Integration Hub page to onboard integrations and populate Snyk AppRisk with data from SCM tools.

You can add an integration by following these steps:

1. Open AppRisk and navigate to the Integrations page.
2. Click **Integration Hub**.
3. Click **Add** on the integration you want to connect.
4. Configure your connection and click **Done**.

See the [Connect an SCM integration](connect-an-scm-integration.md) page or the Connect a third-party integration [connect-a-third-party-integration.md](connect-a-third-party-integration.md "mention") page for step-by-step details about how to set up an integration.

After the integration is validated, a card is displayed on the Integrations page, allowing you to enable or disable the connection, edit the settings, or remove the connection from your configuration.

<figure><img src="../../../.gitbook/assets/image (11) (4).png" alt="AppRisk - Integration status" width="375"><figcaption><p>Snyk AppRisk - Integration status</p></figcaption></figure>

## Using Snyk Broker

If your SCM instance is not publicly accessible, you need Snyk Broker. You can install and configure your Snyk Broker using Docker or Helm. For more information about Snyk Broker, see the Snyk Broker documentation, including [Snyk Broker - AppRisk](../../../enterprise-configuration/snyk-broker/snyk-broker-apprisk.md).

{% hint style="info" %}
Enable the Snyk AppRisk flag in your Snyk Broker deployment environment before running the commands.
{% endhint %}

* GitHub - install and configure Snyk Broker
  * [using Docker](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-prerequisites-and-steps-to-install-and-configure-broker/broker-example-set-up-snyk-broker-with-github.md#docker-run-command-to-set-up-a-broker-client-for-github)
  * [using Helm](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-prerequisites-and-steps-to-install-and-configure-broker/githhub.com-install-and-configure-using-helm.md)
  * [environment variables](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-prerequisites-and-steps-to-install-and-configure-broker/github-environment-variables-for-snyk-broker.md)
* GitHub Enterprise - install and configure Snyk Broker:
  * [using Docker](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-enterprise-prerequisites-and-steps-to-install-and-configure-broker/setup-broker-with-github-enterprise.md#docker-run-command-to-set-up-a-broker-client-for-github-enterprise)
  * [using Helm](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-enterprise-prerequisites-and-steps-to-install-and-configure-broker/github-enterprise-install-and-configure-using-helm.md)
  * [environment variables](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/github-enterprise-prerequisites-and-steps-to-install-and-configure-broker/github-enterprise-environment-variables-for-snyk-broker.md)
* BitBucket - install and configure Snyk Broker:
  * [using Docker](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/bitbucket-server-data-center-prerequisites-and-steps-to-install-and-configure-broker/data-center.md#docker-run-command-to-set-up-a-broker-client-for-bitbucket)
  * [using Helm](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/bitbucket-server-data-center-prerequisites-and-steps-to-install-and-configure-broker/bitbucket-server-data-center-install-and-configure-using-helm.md)
  * [environment variables](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/bitbucket-server-data-center-prerequisites-and-steps-to-install-and-configure-broker/bitbucket-server-data-center-environment-variables-for-snyk-broker-basic-auth.md)
* GitLab - install and configure Snyk Broker:
  * [using Docker](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/gitlab-prerequisites-and-steps-to-install-and-configure-broker/setup-broker-with-gitlab.md#docker-run-command-to-set-up-a-broker-client-for-gitlab)
  * [using Helm](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/gitlab-prerequisites-and-steps-to-install-and-configure-broker/gitlab-install-and-configure-using-helm.md)
  * [environment variables](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/gitlab-prerequisites-and-steps-to-install-and-configure-broker/gitlab-environment-variables-for-snyk-broker.md)
* Azure - install and configure Snyk Broker:
  * [using Docker](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/azure-repos-prerequisites-and-steps-to-install-and-configure-broker/setup-broker-with-azure-repos.md#docker-run-command-to-set-up-a-broker-client-for-azure-repos)
  * [using Helm](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/azure-repos-prerequisites-and-steps-to-install-and-configure-broker/azure-repos-install-and-configure-and-configure-using-helm.md)
  * [environment variables](../../../enterprise-configuration/snyk-broker/install-and-configure-snyk-broker/azure-repos-prerequisites-and-steps-to-install-and-configure-broker/azure-repos-environment-variables-for-snyk-broker.md)

You can find on [GitHub](https://github.com/snyk/broker/tree/565242baf003f06f445489dd96cc68c8386ede38/defaultFilters/apprisk) all the updated `.json` files that include the allowed list of accessible endpoints for the integrations.
