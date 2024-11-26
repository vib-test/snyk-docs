# Advanced configuration for Snyk Broker Docker installation

{% hint style="info" %}
**Multi-tenant settings for EU and AU**\
When you set up Snyk Broker for use in EU or AU Multi-tenant environments, additional environment variables with the specific URLs are required.\
Example: `-e BROKER_SERVER_URL=https://broker.eu.snyk.io`\
For the URLs, see [Regional hosting and data residency](../../../../working-with-snyk/regional-hosting-and-data-residency.md).
{% endhint %}

When you install using Docker, follow these instructions to configure Broker as needed:

* [Changing the auth method with Docker](changing-the-auth-method-with-docker.md)
* [Credential pooling with Docker and Helm](credential-pooling-with-docker-and-helm.md)
* [HTTPS for Broker Client with Docker](https-for-broker-client-with-docker.md)
* [Backend requests with an internal certificate for Docker](backend-requests-with-an-internal-certificate-for-docker.md)
* [Proxy support with Docker](proxy-support-with-docker.md)
* [Disable certificate verification with Docker](disable-certificate-verification-with-docker.md)
* [Custom approved-listing filter with Docker](custom-approved-listing-filter-with-docker.md)
* [Mounting secrets with Docker](mounting-secrets-with-docker.md)
* [Snyk Code - Clone capability with Broker for Docker](snyk-code-clone-capability-with-broker-for-docker.md)
* [Snyk Open Source Scans (SCA) of large manifest files for Docker](snyk-open-source-scans-sca-of-large-manifest-files-docker-setup.md)
* [Insecure Downstream Mode](insecure-downstream-mode.md)
