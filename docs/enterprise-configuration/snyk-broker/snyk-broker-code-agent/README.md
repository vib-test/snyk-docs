# Snyk Broker - Code Agent

{% hint style="info" %}
<mark style="color:red;">**The Code Agent is deprecated**</mark>. The preferred method of running Snyk Code analysis using Snyk Broker is through [Brokered Code](../install-and-configure-snyk-broker/advanced-configuration-for-snyk-broker-docker-installation/snyk-code-clone-capability-with-broker-for-docker.md). The Code Agent is an alternative method without advantages. For details, contact your Snyk Integration Consultant or Technical Success Manager or contact [Snyk Support](https://support.snyk.io/hc/en-us).

The automatic [PR Checks](../../../scan-with-snyk/pull-requests/pull-request-checks/) feature is not supported ifor Snyk Broker - Code Agent.
{% endhint %}

To connect Snyk Code to your self-hosted Git server using Snyk Broker, you can add the Code Agent after installing Snyk Broker for your SCM.

## How the Code Agent works

The Code Agent is available as a [Docker image](https://hub.docker.com/r/snyk/code-agent/). The Code Agent is supported only for Snyk Broker version 4.108.0 and later versions. If you already have a running Broker Client, you must update it by pulling the latest Docker image.

Deploying the Broker client and Code Agent creates two separate services. that, along with the Broker server, [Snyk Code AI Engine](../../../scan-with-snyk/snyk-code/#ai-engine), and Snyk Web UI, enable the following Code Analysis workflow:

1. On the Snyk Web UI, a user initiates a request to import a repository from a self-hosted Git server to Snyk for Code Analysis. The request can also be initiated from the Snyk API v1, by using the [Import targets request](https://snyk.docs.apiary.io/#reference/import-projects/import/import-targets).
2. The request arrives at the Broker server, which sends the request to the Broker client, which sends the request to the Code Agent. The Broker client automatically provides the Code Agent with the connection details to the integrated SCM, which stores the required repositories.
3. The Code Agent connects to the integrated SCM, and securely clones the local repository in your infrastructure. The cloned repository is stored temporarily in the Code Agent container. The cloning is done over an HTTPS connection. If your SCM does not support HTTPS, you use a reverse proxy. For details reach out to your technical contact at Snyk.
4. The Code Agent filters the cloned repository for supported files and sends them to the Snyk Code AI Engine.
5. The Snyk Code AI Engine analyzes the code files in search of vulnerability issues. The analysis results are sent back to the Snyk Web UI. The cloned files are cached according to the Cloud provider's storage minimum policy.

<figure><img src="../../../.gitbook/assets/Code Agent - diagram - new - 4.png" alt="Snyk Code Analysis workflow with Broker"><figcaption><p>Snyk Code Analysis workflow with Broker</p></figcaption></figure>

## Prerequisites for the Code Agent

You have installed a Broker client.

The maximum file size you can import using the Code Agent deployment method is 1MB. For more information, see [File size limit for Snyk Code analysis](../../../supported-languages-package-managers-and-frameworks/technical-specifications.md#file-size-limit-for-snyk-code-analysis).

You must have the ability to run a Docker Container, for example, by using a Docker Desktop or Kubernetes.

{% hint style="info" %}
**Multi-tenant settings for EU and AU**\
When you set up Broker, Code Agent, or both for use in EU or AU Multi-tenant environments, additional environment variables with the specific URLs are required.\
Example: `-e BROKER_SERVER_URL=https://broker.eu.snyk.io`\
For the URLs, see [Regional hosting and data residency](../../../working-with-snyk/regional-hosting-and-data-residency.md).
{% endhint %}

You cannot deploy the Code Agent as a part of a Broker redundancy solution.

The minimum requirements for running the **Code Agent** component are:

* **CPU** - 1 vCPU
* **Memory** - 2Gb
* **Disk space** - 2Gb\
  The available disk space determines the maximum size of repositories that are imported simultaneously. To import repositories that exceed this size, you must increase the available disk space. However, it is highly recommended to consult with your Snyk team before importing repositories that are larger than 2Gb.
* **Network:**
  * SCM connection - HTTPS communication to the SCM that stores the repositories you want to analyze. Support for HTTP-only SCM-deployments can be resolved by deploying a reverse proxy between the Code Agent and the SCM.
  * If you are using the same Broker Client for other Snyk products, and you want to enable Automatic PR Checks on that Client, you must also configure the following:\
    An internal connection that allows inbound access from the integration (SCM) to the Broker Client at the BROKER\_CLIENT\_URL on the port you have configured (typically 8000). This is not inbound from the internet. See [Running the Broker Client](install-snyk-broker-code-agent-using-docker/set-up-the-broker-client/run-the-broker-client-without-the-code-snippet-display.md).
  * Snyk Code Analysis Engine connection - outbound communication to the Code Analysis Engine at [https://deeproxy.snyk.io/](https://deeproxy.snyk.io/).
* Internet bandwidth and connection - the upload speed of the source code to the Broker Server will be affected by low bandwidth and a slow Internet connection.
* **Snyk API token** - your Snyk API token is required to authenticate the Code Agent component with your Snyk Account. For more information see [Obtaining your Snyk API token](../../../getting-started/how-to-obtain-and-authenticate-with-your-snyk-api-token.md).
