# Container security integrations

## Overview of Snyk Container integrations

Snyk Container provides a range of integrations to import Projects into Snyk. These integrations support different workflows for Snyk users and customers.

The integrations you use depend on your requirements and workflow. You can start with one integration and move to others later or use a combination of integrations as your team grows.

For example, it’s common to use Snyk CI integrations to provide fast feedback to development teams when you build an image and then use the Kubernetes integration to provide assurance for running images in production.

The main Container integrations are:

* **CLI:** Use for local investigation or testing an image you have built. This integration enables you to get early feedback on your machine and use as a gatekeeping stage in CI. It also serves a tool in CD for Snyk to capture snapshots and identify newly discovered vuilnerabilities. For details, see [Snyk CLI for container security](../../snyk-cli/scan-and-maintain-projects-using-the-cli/snyk-cli-for-snyk-container/).
* **SCM:** Snyk can detect Dockerfiles directly from Git repositories and provide recommendations for updating the base image to a less vulnerable one. For details, see [Scan your Dockerfile](../../scan-with-snyk/snyk-container/scan-your-dockerfile/).
* **Container registries:** Use to test a large number of images, or if you cannot modify many CI pipelines.
* **Kubernetes:** Monitor running workloads with additional context around how the workload has been configured to run. For details, see Overview of the Kubernetes integration.

{% hint style="info" %}
For cloud-hosted container registries, Snyk does not import and scan images that are larger than 2GB in size. To scan images that exceed this size, use the [Snyk CLI](../../snyk-cli/scan-and-maintain-projects-using-the-cli/snyk-cli-for-snyk-container/).
{% endhint %}

## Choose your Snyk Container integration

Depending on your needs and context, in order to monitor for new vulnerabilities in build container images, Snyk recommends choosing one of the following integration points: CLI, a container registry integration, or a Kubernetes integration. By choosing only one of these testing methods, you can ensure the best outcome when identifying vulnerabilities and reduce noise.

Because the Snyk CLI is highly customizable with CLI flags, it is the most broad in scope of all the integrations. You can run `snyk container monitor` as part of the Continuous Deployment pipeline and capture a snapshot of the container image as it’s being deployed. For more information, see [Snyk CLI for Snyk Container](../../snyk-cli/scan-and-maintain-projects-using-the-cli/snyk-cli-for-snyk-container/).
