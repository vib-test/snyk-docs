# GitHub - prerequisites and steps to install and configure Broker

Before installing, **review the general instructions** for the installation method you plan to use, [Helm](../install-and-configure-broker-using-helm.md) or [Docker](../install-and-configure-broker-using-docker.md).

The **prerequisites** follow.

Before installing the Snyk GitHub Broker, you must configure a GitHub service account token with the [required permissions](../../../../scm-ide-and-ci-cd-workflow-and-integrations/snyk-scm-integrations/snyk-github-integration.md#required-permissions-scope-for-the-github-integration). All the operations, both those that are triggered through the Snyk Web UI and the automatic operations, are performed for a GitHub service account that has its token configured with the Broker.

You must have Docker or a way to run Docker Linux containers. Some Docker deployments for Windows run only Windows containers. Ensure that your deployment is capable of running Linux containers.

**Continue** with the steps to install using [Docker](broker-example-set-up-snyk-broker-with-github.md) or [Helm](githhub.com-install-and-configure-using-helm.md).
