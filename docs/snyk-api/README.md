# Snyk API

{% hint style="info" %}
The Snyk API is available only for Enterprise plans.

For more information, see [Plans and pricing](https://snyk.io/plans).
{% endhint %}

The Snyk API allows Enterprise customers to integrate programmatically with Snyk.

Snyk [extensibility and the Snyk API](https://snyk.io/blog/extensibility-and-the-snyk-api/) enable developers to tune Snyk security automation to their specific workflows, ensuring consistency in both developer experience and platform governance. The [Snyk REST API](./#snyk-rest-api) and the [V1 API ](./#snyk-v1-api-superseded-by-the-rest-api)are available for you to use when you decide to [use an API rather than the CLI or an integration](./#when-to-use-the-api-versus-the-cli-or-an-integration).

## Snyk REST API

The REST API is based on the OpenAPI and JSON:API standards and represents an evolutionary approach to API development, with each endpoint versioned.

## When to use the API versus the CLI or an integration

Use the API when you want to customize, integrate, and automate Snyk security as part of your specific workflows.

Note that there may be differences in the output of the API, the CLI, and integrations.

For example, for many package managers using the API will be less accurate than running the Snyk CLI as part of your build pipe or locally on your package. More than one version of a package may fit the requirements in manifest files. Running the CLI locally tests the actual deployed code, and has an accurate snapshot of the dependency versions in use. The API infers a snapshot, with inferior accuracy. Note that the Snyk CLI can output machine-readable JSON (`snyk test --json`).

You can allow Snyk access to your development flow by using Snyk integrations. The advantage is having Snyk monitor every new pull request and suggest fixes by opening new pull requests. You can integrate Snyk directly with your source code management (SCM) tool, or by using a Broker to allow greater security and auditability.
