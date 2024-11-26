# Bitbucket Server/Data Center - install and configure using Helm

Before installing, review the [prerequisites](./) and the general instructions for installation using [Helm](../install-and-configure-broker-using-helm.md).

To use this chart, you must first add the Snyk Broker Helm Chart by adding the repo:

`helm repo add snyk-broker https://snyk.github.io/snyk-broker-helm/`

Then, run the following commands to install the Broker and customize the environment variables. For definitions of the environment variables, refer to [Bitbucket Server/Data Center - environment variables for Snyk Broker Basic Auth](bitbucket-server-data-center-environment-variables-for-snyk-broker-basic-auth.md) and [Bitbucket Server/Data Center - environment variables for Snyk Broker Personal Access Token (PAT)](bitbucket-server-data-center-environment-variables-for-snyk-broker-personal-access-token-pat.md).

For `bitbucket` and `bitbucketApi` values do not include `https://`

Snyk AppRisk is set by default to `false`. Enable it by setting the flag to `true`.

Use the following command to **configure Broker to be used with Bitbucket Server using Basic Auth**:

```
helm install snyk-broker-chart snyk-broker/snyk-broker \
             --set scmType=bitbucket-server \
             --set brokerToken=<ENTER_BROKER_TOKEN> \
             --set bitbucketUsername=<ENTER_USERNAME> \
             --set bitbucketPassword=<ENTER_PASSWORD> \
             --set bitbucket=<ENTER_BITBUCKET_URL> \
             --set bitbucketApi=<ENTER_BITBUCKET_API_URL> \
             --set brokerClientUrl=<ENTER_BROKER_CLIENT_URL>:<ENTER_BROKER_CLIENT_PORT> \
             --set enableAppRisk=true \
             -n snyk-broker --create-namespace
```

Use the following command to **configure Broker to be used with Bitbucket Server using Bearer Auth (Personal Access Token)**:

```
helm install snyk-broker-chart snyk-broker/snyk-broker \
             --set scmType=bitbucket-server-bearer-auth \
             --set brokerToken=<ENTER_BROKER_TOKEN> \
             --set bitbucketPat=<ENTER_PAT> \
             --set bitbucket=<ENTER_BITBUCKET_URL> \
             --set bitbucketApi=<ENTER_BITBUCKET_API_URL> \
             --set brokerClientUrl=<ENTER_BROKER_CLIENT_URL>:<ENTER_BROKER_CLIENT_PORT> \
             --set enableAppRisk=true \
             -n snyk-broker --create-namespace
```

You can pass any environment variable of your choice in the Helm command. For details, see [Custom additional options for Broker Helm Chart](../advanced-configuration-for-helm-chart-installation/custom-additional-options-for-broker-helm-chart-installation.md). Follow the instructions for [Advanced configuration for Helm Chart installation](../advanced-configuration-for-helm-chart-installation/) to make configuration changes as needed.

You can verify that the Broker is running by looking at the settings for your brokered integration in the Snyk Web UI to see a confirmation message that you are connected. You can start importing Projects once you are connected.
