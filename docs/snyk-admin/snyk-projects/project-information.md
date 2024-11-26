# Project information

The **Projects** page lists imported Projects and information about the Projects, such as vulnerabilities and license issues. On this page, you can group, filter, and sort your Projects and activate, deactivate, change test frequency, or delete them.

## Filter existing Projects

On the **Projects** page, you can filter your Projects by whether or not they contain issues and by the type of Git integration. The following filters are available:

* **Show**:
  * **With issues** - displays only Projects with issues.
  * **Without issues** - displays only Projects without issues.
* **Integrations** - displays the integrated Git repositories imported to Snyk.

To reset all filter criteria, click **Reset**.

<figure><img src="../../.gitbook/assets/Project filtering.png" alt="Filter pane on Projects page"><figcaption><p>Filter pane on the Projects page</p></figcaption></figure>

{% hint style="info" %}
Only active Projects with discovered issues are displayed on the Projects page by default.
{% endhint %}

## View Project details

To view detailed information for a Project, click a Project entry. The page that opens displays the detailed Project information.

<figure><img src="../../.gitbook/assets/Detailed Project_info.png" alt="Detailed information for the package.json Project"><figcaption><p>Detailed information for the <strong><code>package.json</code></strong> Project</p></figcaption></figure>

The following information is available:

* **Header**: displays a summary of the Project. See [Project summary](project-information.md#view-project-summary).
* **Issue cards**: display summaries of issues found. See [Issue card information](issue-card-information.md).
* **Views** (links at top right):
  * **Overview**: displays [Project issues, fixes, and dependencies](view-project-issues-fixes-and-dependencies.md).
  * **History**: displays historical snapshots of recent tests. See [View Project history](view-project-history.md).
  * **Settings**: displays [Project settings](view-and-edit-project-settings.md).

## View Project summary

<figure><img src="../../.gitbook/assets/Header_Project_details.png" alt="Project summary for the package.json Project"><figcaption><p>Project summary for the <code>package.json</code> Project</p></figcaption></figure>

In the header of each Project overview, you can view information about:

* File and history details
  * Name and external link of the monitored repository
  * Name of the monitored branch
  * Direct link to the Project file in the SCM
  * The time when the Project was first imported to Snyk
  * The last time Snyk took a snapshot of the file that was fetched from the SCM and tested it
* Project import
  * **IMPORTED BY**: The user who imported the Project.
  * **PROJECT OWNER.** You can add an owner for this Project from a list of users who have access to the Project by clicking **Add a project owner**. You can also view this information through the [List all Projects](https://apidocs.snyk.io/#get-/orgs/-org_id-/projects) endpoint in the Snyk API.
* Predefined [Project attributes](project-attributes.md) and any additional [Project tag](../introduction-to-snyk-projects/project-tags.md) metadata.
