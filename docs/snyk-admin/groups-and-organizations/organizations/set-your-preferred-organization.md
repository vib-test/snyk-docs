# Set your preferred Organization

## Set your preferred Organization

If you have several Organizations, one of these Organizations is set by default as your **Preferred Organization** in your Snyk account. A Preferred Organization determines the following:

* On the Snyk Web UI: The Organization that is displayed by default when you log in to your Snyk account.
* In the Snyk CLI: The Organization that is used by default for the test count when you scan through the CLI.\
  **Note**: To change the Organization used for the test count in the CLI, use the\
  `--org=<ORG_ID>` option. For more information, see the CLI help for the test commands: [Snyk test](../../../snyk-cli/commands/test.md), [Snyk Code test](../../../snyk-cli/commands/code-test.md), [Snyk Container test](../../../snyk-cli/commands/container-test.md), or [Snyk IaC test](../../../snyk-cli/commands/iac-test.md).

Follow these steps to change your Preferred Organization:

1\. On the Snyk Web UI, click your Account icon at the bottom left corner of the screen. Then select the **Account settings** option:

<figure><img src="../../../.gitbook/assets/snyk-account-settings.png" alt="Account settings"><figcaption><p>Account settingd</p></figcaption></figure>

2\. On the **Account Settings** page, in the **Preferred Organization** section, open the Organization dropdown list to display a list of the Organizations to which you have access, and select the Organization you want to set as your Preferred Organization:

<figure><img src="../../../.gitbook/assets/image (20) (1) (1).png" alt="Change your Preferred Organization"><figcaption><p>Change your Preferred Organization</p></figcaption></figure>

3\. Click the **Update Preferred Org** button to save your new setting.

The Organization you selected as your **Preferred Organization** is displayed when you log in to your Snyk account and used by default for the test count when you scan using the CLI.
