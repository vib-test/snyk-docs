# Connect a third-party integration

{% hint style="warning" %}
**Release status**\
The third-party integrations are available in Closed Beta and are applicable only to the Snyk AppRisk Pro version. Contact your salesperson if you are interested in Snyk AppRisk Pro.
{% endhint %}

The Integrations page shows all active integrations, including data from your existing Snyk Organizations that is automatically synced and provides access to the Integration Hub.

{% hint style="info" %}
The Loaded package risk factor is not supported by Snyk for open-source packages, only for application packages such as npm, Maven, or PyPI.
{% endhint %}

You can customize your AppRisk integrations from the **Integrations Hub** where the following SAST and Secrets integrations are available:

SAST:

* [Veracode SAST](connect-a-third-party-integration.md#veracode-setup-guide)
* [Checkmarx SAST](connect-a-third-party-integration.md#checkmarx-setup-guide)
* [SonarQube](connect-a-third-party-integration.md#sonarqube-setup-guide)

Secrets:

* [Nightfall](connect-a-third-party-integration.md#nightfall-setup-guide)
* [GitGuardian](connect-a-third-party-integration.md#gitguardian-setup-guide)

Runtime:

* [Dynatrace](connect-a-third-party-integration.md#dynatrace-setup-guide)
* [Sysdig](connect-a-third-party-integration.md#sysdig-setup-guide)

ITSM:

* [Jira](connect-a-third-party-integration.md#jira-setup-guide)

{% hint style="info" %}
Data synchronization may take up to two hours after receiving the **Connected** status from a new integration setup.
{% endhint %}

## Veracode setup guide

### Prerequisites <a href="#verocode-prerequisites" id="verocode-prerequisites"></a>

The Veracode application concept is matched into the Snyk AppRisk repository assets. You need to create and utilize the Veracode custom field by using the [Veracode API](https://app.swaggerhub.com/apis/Veracode/veracode-applications_api_specification/1.0#/Application%20information%20API/updateApplicationUsingPUT). More details about the Veracode custom field are available [here](https://docs.veracode.com/r/t_create_custom_metadata).

Ensure you are adding a custom field called repoURL:

```
{
"name": "repoURL", 
"value": <YOUR GITHUB URL>
}

```

### Required parameters <a href="#veracode-required-parameters" id="veracode-required-parameters"></a>

* API ID and API Key - API credentials associated with a user account. For more information, access this link: [https://help.veracode.com/r/c\_api\_credentials3](https://help.veracode.com/r/c_api_credentials3).

### Integration Hub setup <a href="#veracode-integration-hub-setup" id="veracode-integration-hub-setup"></a>

1. Open the **Integration Hub** menu.
2. Select the **SAST** tag and search for Veracode.
3. Click the **Add** button.
4. Add the profile name for this integration.
5. Add the **API ID** from your Veracode account.
6. Add the **API key** from your Veracode account.
7. Click the **Done** button.
8. When the connection is established, the status of the Veracode integration is changed to **Connected**.

## Checkmarx setup guide

Use the following instructions to set up your Checkmarx SAST integration. Checkmarx SAST integration is only working for the Checkmarx SAST, we are not yet supporting Checkmarx One.

{% hint style="info" %}
Snyk AppRisk Pro does not currently support the Checkmarx One integration.
{% endhint %}

### Prerequisites <a href="#checkmarx-prerequisites" id="checkmarx-prerequisites"></a>

* Install and configure your [Snyk Broker](../../../enterprise-configuration/snyk-broker/snyk-broker-apprisk.md#checkmarx-sast-integration) connection for Snyk AppRisk.
* Ensure you have properly used Git Setting for your Checkmarx Project based on the Checkmarx [documentation](https://checkmarx.stoplight.io/docs/checkmarx-sast-api-reference-guide/8312d35369b9b-set-project-s-remote-source-settings-as-git).

### Required parameters <a href="#checkmarx-required-parameters" id="checkmarx-required-parameters"></a>

1. API URL - The URL of Checkmarx API, for example, `checkmarx.customer.com`.
2. Username and Password - Credentials for a user account with Checkmarx SAST access.

### Integration Hub setup <a href="#checkmarx-integration-hub-setup" id="checkmarx-integration-hub-setup"></a>

After you have installed and configured Snyk Broker for AppRisk and you successfully established a connection for Checkmarx SAST, you also need to configure the integration from the Snyk AppRisk Integration Hub.

1. Open the **Integration Hub** menu.
2. Select the **SAST** tag and search for Checkmarx.
3. Click the **Add** button.
4. Add the profile name for this integration.
5. Add the Broker token for the Snyk AppRisk Checkmarx integration.
6. Add the Checkmarx host. For example `checkmarx.customer.com`
7. Click the **Done** button.
8. When the connection is established, the status of the Checkmarx integration is changed to **Connected**.

## SonarQube setup guide

### Required parameters <a href="#sonarqube-required-parameters" id="sonarqube-required-parameters"></a>

* API Key. [Here](https://docs.sonarsource.com/sonarqube/latest/user-guide/user-account/generating-and-using-tokens/) you can find more details about the SonarQube API Key.

### Integration Hub setup <a href="#sonarqube-integration-hub-setup" id="sonarqube-integration-hub-setup"></a>

* Open the **Integration Hub** menu.
* Select the **SAST** tag and search for SonarQube.
* Click the **Add** button.
* Add the **Profile name** for this integration.
* Add the **Host URL** for this integration.
* Add the **API token**. Navigate to your SonarQube account, select User, select My Account, select Security, and then User Token. [Here](https://docs.sonarsource.com/sonarqube/latest/user-guide/user-account/generating-and-using-tokens/) you can find more details about the SonarQube API Key.
* Click the **Done** button.
* When the connection is established, the status of the SonarQube integration is changed to **Connected**.

## Nightfall setup guide

### Required parameters <a href="#nightfall-required-parameters" id="nightfall-required-parameters"></a>

* API Key. [Here](https://docs.nightfall.ai/docs/creating-an-api-key) you can find more details about how to create a Nightfall API key.

### Integration Hub setup <a href="#nightfall-integration-hub-setup" id="nightfall-integration-hub-setup"></a>

1. Open the **Integration Hub** menu.
2. Select the **Secrets** tag and search for Nightfall.
3. Click the **Add** button.
4. Add the **Profile name** for this integration.
5. Add the **Base API URL** for this integration.
6. Add the **API Key** for this integration.
7. Click the **Done** button.
8. When the connection is established, the status of the Nightfall integration is changed to **Connected**.

The following video provides an overview of the Nightfall configuration from the Integration Hub:

{% embed url="https://www.youtube.com/watch?v=FJ5fAyMYSUs" %}
Liked the video? Checkout the rest of the course on [Snyk Learn](https://learn.snyk.io/catalog/?type=product-training\&topics=AppRisk)!
{% endembed %}

After you set up your Nightfall integration using the Integration Hub, you can see the secrets detection coverage.

{% embed url="https://www.youtube.com/watch?v=o6TqPMSq1rk" %}
Liked the video? Checkout the rest of the course on [Snyk Learn](https://learn.snyk.io/catalog/?type=product-training\&topics=AppRisk)!
{% endembed %}

## GitGuardian setup guide

### Required parameters <a href="#gitguardian-required-parameters" id="gitguardian-required-parameters"></a>

* API Key. [Here](https://docs.gitguardian.com/api-docs/authentication) you can find more details about how to create a GitGuardian API Key.

When you create a GitGuardian API Key, remember that it works for both service accounts and personal access token.

Ensure that the following permissions are set as READ:

* Incident (`mandatory`)
* Teams (`recommended` for GitGuardian paid accounts)

### Integration Hub setup <a href="#gitguardian-integration-hub-setup" id="gitguardian-integration-hub-setup"></a>

1. Open the **Integration Hub** menu.
2. Select the **Secrets** tag and search for GitGuardian.
3. Click the **Add** button.
4. Add the **Profile name** for this integration.
5. Add the **API Token** for this integration.
6. Click the **Done** button.
7. When the connection is established, the status of the GitGuardian integration is changed to **Connected**.

The following video provides an overview of the GitGuardian configuration from the Integration Hub:

{% embed url="https://www.youtube.com/watch?v=4u4QrJBZTkI" %}
Liked the video? Checkout the rest of the course on [Snyk Learn](https://learn.snyk.io/catalog/?type=product-training\&topics=AppRisk)!
{% endembed %}

After you set up your GitGuardian integration using the Integration Hub, you can see the secrets detection coverage:

{% embed url="https://www.youtube.com/watch?v=zh4c5f_vv1k" %}
Liked the video? Checkout the rest of the course on [Snyk Learn](https://learn.snyk.io/catalog/?type=product-training\&topics=AppRisk)!
{% endembed %}

## Jira setup guide

### Required parameters <a href="#jira-required-parameters" id="jira-required-parameters"></a>

* API Key - Access [https://id.atlassian.com/manage-profile/security/api-tokens](https://id.atlassian.com/manage-profile/security/api-tokens) to generate a Jira API Token.

{% hint style="info" %}
Ensure you have the correct user permissions before creating the API Token.
{% endhint %}

### Integration Hub setup <a href="#jira-integration-hub-setup" id="jira-integration-hub-setup"></a>

* Open the **Integration Hub** menu.
* Select the **ITSM** tag and search for Jira.
* Click the **Add** button.
* Add the **Profile name** for this integration.
* Add the **API Token** for this integration.
* Add the **User Email** used for this integration.
* Add the **Host URL** for this integration.
* Click the **Done** button.
* When the connection is established, the status of the Nightfall integration is changed to **Connected**.

{% hint style="info" %}
You can add only one Jira profile to the Jira integration.
{% endhint %}

### Types of Jira integrations

Multiple Jira integrations are available when using Snyk, each designed to support specific needs.

* Jira - Manually create a ticket for issues from Snyk.
* [Jira Script](../../../integrate-with-snyk/jira-and-slack-integrations/jira-integration.md) - Automatically create tickets for new vulnerabilities.
* [Security in Jira](../../../integrate-with-snyk/jira-and-slack-integrations/snyk-security-in-jira-cloud-integration.md) - View vulnerability information in Jira and create a ticket from Jira. The ticket is not visible in Snyk.
* [Jira for Snyk AppRisk](connect-a-third-party-integration.md#jira-setup-guide) - As part of the policy action, you can automatically create Jira tickets from Snyk AppRisk Assets.

The following table presents the functionality of all types of Jira integrations available in Snyk, specifies the supported Jira platform, the expected outcome, the authentication type, and the level of availability in Snyk.

| Jira integration type                                                                                                   | Functionality                                                                                                                                                                                                                                                                         | Authentication                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Jira                                                                                                                    | <p>Create a manual ticket for issues from Snyk.<br><br><strong>Supported for</strong>:<br>- Jira On-Cloud<br>- Jira Data Centre<br><br><strong>Outcome</strong>:<br>- Create Issue tickets</p>                                                                                        | <p><strong>Authentication type</strong>: Personal Access Token</p><p><br><strong>Availability level</strong>: Snyk Organization</p>                                     |
| [Jira Script](../../../integrate-with-snyk/jira-and-slack-integrations/jira-integration.md)                             | <p>Automatically create tickets for new vulnerabilities.<br><br><strong>Supported for</strong>:<br>- Jira On-Cloud<br>- Jira Data Centre<br><br><strong>Outcome</strong>:<br>- Create Issue tickets</p>                                                                               | <p><strong>Authentication type</strong>: Personal Access Token</p><p><br><strong>Availability level</strong>: Snyk Organization</p>                                     |
| [Security in Jira](../../../integrate-with-snyk/jira-and-slack-integrations/snyk-security-in-jira-cloud-integration.md) | <p>View vulnerability information in Jira and create a ticket from Jira.<br>* Jira ticket is not visible in Snyk.<br><br><strong>Supported for</strong>:<br>- Jira On-Cloud<br><br><strong>Outcome</strong>:<br>- Create Issue tickets</p>                                            | <p><strong>Authentication type</strong>: JWT(JSON Web Token) as part of the Connect App framework.</p><p><br><strong>Availability level</strong>: Snyk Organization</p> |
| [Jira for Snyk AppRisk](connect-a-third-party-integration.md#jira-setup-guide)                                          | <p>Use the "Create Jira ticket" action from a Snyk policy to create Jira tickets from Snyk AppRisk Assets automatically.<br><br><strong>Supported for</strong>:<br>- Jira On-Cloud<br>- Jira Data Centre (coming soon)<br><br><strong>Outcome</strong>:<br>- Create Asset tickets</p> | <p><strong>Authentication type</strong>: Personal Access Token</p><p><br><strong>Availability level</strong>: Snyk Group</p>                                            |

## Dynatrace setup guide

### Prerequisites <a href="#dynatrace-prerequisites" id="dynatrace-prerequisites"></a>

* Use Dynatrace SaaS on the DPS licensing model.
* The Dynatrace [Kubernetes app](https://docs.dynatrace.com/docs/platform-modules/infrastructure-monitoring/container-platform-monitoring/kubernetes-app/overview) is configured to monitor at least one cluster.
* The user is associated with a group that has permissions (through policies) to query the entity model. In the Dynayrace policy, set the following permission: `storage:entities:read`.

Comply with the following steps before integrating Dynatrace with Snyk AppRisk:

1. Retrieve the `account-uuid` from your Dynatrace account. Navigate to [https://myaccount.dynatrace.com/accounts](https://myaccount.dynatrace.com/accounts) and select the account whose environment you want to integrate into Snyk. Identify the `account-uuid` in the URL and save it for later use.
2. Ensure you have OneAgent deployed in your Kubernetes environment. Navigate to `Settings` then `Environments` and select the environment you want to integrate into Snyk. Save the environment ID for later use (available in the URL of the new window as well). Click `Deploy OneAgent` then `Kubernetes` and follow the instructions. Ensure OneAgent is running in full-stack mode.
3. Ensure your deployment is activated. On your environment's page, click `Kubernetes` , then `Recommendations` and activate the cluster where you deployed OneAgent.
4. Create an OAuth client with the right permissions. Navigate to [https://myaccount.dynatrace.com/accounts](https://myaccount.dynatrace.com/accounts), then to `Identity & access management`. Select `OAuth clients` and click `Create client`. Fill in the details and check the following permissions; then click `Create client`:

<pre><code><strong>storage:entities:read
</strong></code></pre>

5. Save the Client ID and Client secret for later and click `Finish`.

### Required parameters <a href="#dynatrace-required-parameters" id="dynatrace-required-parameters"></a>

1. **Account UUID** - the `account-uuid` of your Dynatrace account.
2. **Environment ID** - the ID of the environment monitored in Dynatrace.
3. **OAuth client ID** - the ID of the OAuth client created in the prerequisites.
4. **OAuth client secret** - the secret of the OAuth client created in the prerequisites.

### Integration Hub setup <a href="#dynatrace-integration-hub-setup" id="dynatrace-integration-hub-setup"></a>

* Open the **Integration Hub** menu.
* Select the **Runtime** tag and search for **Dynatrace**.
* Click the **Add** button.
* Edit the **Profile name** of your integration.
* Enter the **Account UUID**.
* Enter the **Environment ID**.
* Enter the **OAuth client ID**.
* Enter the **OAuth client secret**.
* Click the **Done** button.
* When the connection is established, the **Dynatrace** integration status changes to **Connected**.

{% hint style="info" %}
After the Dynatrace runtime data becomes available from the runtime integration, it will appear in Snyk AppRisk within a few hours.
{% endhint %}

## Sysdig setup guide

### Prerequisites <a href="#sysdig-prerequisites" id="sysdig-prerequisites"></a>

* The account must have access to Sysdig Secure product.
* Contact your Sysdig representative to activate the in-use packages feature flag

### Required parameters <a href="#sysdig-required-parameters" id="sysdig-required-parameters"></a>

* **Account API Token** - [Here](https://docs.sysdig.com/en/docs/administration/administration-settings/user-profile-and-password/retrieve-the-sysdig-api-token/) you can find details on how to retrieve your Sysdig API Token.

{% hint style="info" %}
The `Account API Token` must be a `Sysdig Secure API token` and not a `Sysdig Monitor API Token`.
{% endhint %}

* **Region -** [**Here**](https://docs.sysdig.com/en/docs/administration/saas-regions-and-ip-ranges) you can find details about the Sysdig region URLs.

### Known limitations

* If the Sysdig Agent is not deployed on every node of a cluster, runtime data available from this integration may be incomplete.
* Various Sysdig scans run at different intervals, which may cause a delay between applying changes to a resource within a cluster and reporting this information through the integration.

### Integration Hub setup <a href="#sysdig-integration-hub-setup" id="sysdig-integration-hub-setup"></a>

* Open the **Integration Hub** menu.
* Select the **Runtime** tag and search for Sysdig.
* Click the **Add** button.
* Add the **Profile name** for this integration.
* Add the **Account API Token**.
* Set the **Sysdig region**.
* Click the **Done** button.
* When the connection is established, the status of the Sysdig integration is changed to **Connected**.

{% hint style="info" %}
After the Sysdig runtime data becomes available from the runtime integration, it will appear in Snyk AppRisk within a few hours.
{% endhint %}
