# GitLab - install and configure using Helm

Before installing, review the [prerequisites](./) and the general instructions for installation using [Helm](../install-and-configure-broker-using-helm.md).

To use this chart, you must first add the Snyk Broker Helm Chart by adding the repo:

`helm repo add snyk-broker https://snyk.github.io/snyk-broker-helm/`

Then, run the following commands to install the Broker and customize the environment variables. Refer to [GitLab - environment variables for Snyk Broker](gitlab-environment-variables-for-snyk-broker.md) for definitions of the environment variables.

For the `gitlab` value, do not include `https://.`

`brokerToken` is a Helm variable that feeds into and sets the `BROKER_TOKEN` environment variable. It is the Helm way to pass the token.

`ACCEPT_CODE` is [set to true by default](https://github.com/snyk/snyk-broker-helm/blob/465d4ef279755fa5c9507975a88348bab04c2264/charts/snyk-broker/templates/broker_deployment.yaml#L383) in the chart, as is [ACCEPT\_IAC](https://github.com/snyk/snyk-broker-helm/blob/465d4ef279755fa5c9507975a88348bab04c2264/charts/snyk-broker/templates/broker_deployment.yaml#L386C23-L386C43). You can disable them if needed using `disableAutoAcceptRules=true`, but otherwise, these are enabled.

Use the environment variable `REMOVE_X_FORWARDED_HEADERS=true` to remove the `XFF` headers from the requests made by the Broker client to GitLab. This allows the Broker to work properly.

Snyk AppRisk is set by default to `false`. Enable it by setting the flag to `true`.

```
helm install snyk-broker-chart snyk-broker/snyk-broker \
             --set scmType=gitlab \
             --set brokerToken=<ENTER_BROKER_TOKEN> \
             --set gitlab=<ENTER_GITLAB_URL> \
             --set scmToken=<ENTER_GITLAB_TOKEN> \
             --set brokerClientUrl=<ENTER_BROKER_CLIENT_URL>:<ENTER_BROKER_CLIENT_PORT> \
             --set enableAppRisk=true \
             -n snyk-broker --create-namespace
```

You can pass any environment variable of your choice in the Helm command. For details, see [Custom additional options for Broker Helm Chart](../advanced-configuration-for-helm-chart-installation/custom-additional-options-for-broker-helm-chart-installation.md). Follow the instructions for [Advanced configuration for Helm Chart installation](../advanced-configuration-for-helm-chart-installation/) to make configuration changes as needed.

You can verify that the Broker is running by looking at the settings for your brokered integration in the Snyk Web UI to see a confirmation message that you are connected. You can start importing Projects once you are connected.
