# Remove imported repository from a Project

If you do not want Snyk to continue testing one or more of your imported repositories, you can do one of the following:

* Remove the entire repository from your Snyk Account in one of the following ways:
  * Deactivate the repository.
  * Delete the repository from your Snyk Account.

{% hint style="info" %}
If you remove the entire repository from your Account, your repository will no longer be analyzed by any of the Snyk products.
{% endhint %}

* Remove only the **Code analysis** Project from your Snyk Account in one of the following ways:
  * Deactivate the Project.
  * Delete the Project from your Snyk Account.

{% hint style="info" %}
If you remove only the **Code analysis** Project, other Snyk products that are enabled in your account will continue to analyze the imported repository.
{% endhint %}

## **Remove imported repository methods**

To select the right method for you for removing repositories from Snyk testing, consider what will happen in each of the following actions:

* Deactivating an imported repository will:
  * Remove the webhook from Snyk to the SCM repository.
  * Disable pull request tests for new vulnerabilities.
  * Disable the Fix Pull Requests option from being opened for newly discovered vulnerabilities
  * Disable recurring tests; email alerts about newly discovered vulnerabilities will be turned off.
* Deleting a Snyk Project or an imported repository will:
  * Delete the entire Project or repository and all its historical snapshot data from Snyk.
  * Remove the webhook from the SCM repository.

{% hint style="info" %}
Deleting a Snyk Project or an imported repository will not have any effect on your source code.

If you want to remove specific directories or files from the Snyk Code test, use [the exclude option in the `.snyk` file](exclude-directories-and-files-from-project-import.md).
{% endhint %}

## **Deactivate and delete imported repositories**

For instructions on deleting repositories, see the Project actions [Delete, Activate, or Deactivate](../../snyk-admin/snyk-projects/#delete-activate-or-deactivate). For more details, see [How can I delete multiple Projects](https://support.snyk.io/hc/en-us/articles/360002623578-How-can-I-delete-multiple-projects)?

## **Deactivate and delete a Snyk Code Project**

To stop Snyk Code from testing an imported repository, you can either deactivate or delete the **Code analysis** Project in the repository. The **Code analysis** Project will no longer be active in the repository and Snyk Code will stop testing the repository, but other Snyk products will continue to scan the repository files.

Follow these steps to deactivate or delete the Code analysis Project:

1\. On the **Projects** page, locate the repository you want Snyk Code to stop testing. In its Target folder, locate the **Code analysis** Project, and click the **Settings** button at the end of its row:

<figure><img src="../../.gitbook/assets/image (404) (1) (1).png" alt="Settings button for Code analysis Proejct"><figcaption><p>Settings button for Code analysis Proejct</p></figcaption></figure>

2\. On the **Settings** page of the **Code analysis** Project, click either the **Deactivate project** or **Delete project** button according to your needs:

<figure><img src="../../.gitbook/assets/image (449).png" alt="Deactivate project and Delete project buttons on Code analysis Project Settings page"><figcaption><p>Deactivate project and Delete project buttons on Code analysis Project Settings page</p></figcaption></figure>

The **Code analysis** Project you selected is either deactivated or deleted, and its repository will no longer be tested by Snyk Code.

If you want Snyk Code to resume its testing after you delete or deactivate the **Code analysis** Project of a repository, do the following:

* After deleting the Code analysis Project, re-import the repository to Snyk and then refresh the **Projects** page to view the results of the re-import.
* **After deactivating the Code analysis Project,** re-activate the **Code analysis** Project via the **Settings** page of the Project. After you deactivate a Project, the **Deactivate project** button changes to **Activate project**, and a new **Activate** button appears at the top of the page. Click one of these buttons to re-activate the Project:

<figure><img src="../../.gitbook/assets/image (86).png" alt="Activate project button on Code analysis Project Settings page"><figcaption><p>Activate project button on Code analysis Project Settings page</p></figcaption></figure>
