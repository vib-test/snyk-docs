# Customize PR templates

When you fix or upgrade Snyk Open Source and Snyk Container Projects imported using the [SCM integrations](../../../../scm-ide-and-ci-cd-workflow-and-integrations/snyk-scm-integrations/), Snyk raises pull requests (PRs) against your repository.

Snyk has default PR templates for the title, description, and commit message. These indicate what packages are being changed, which issues are being fixed, and many other details.

You may have your own standards and practices for submitting pull requests. For instance, if a pull request comes from Snyk, you may require the title to begin with `SNYK:`.

You can set custom PR templates using the following methods:

* API request - set all PRs in the Group to the custom template that is uploaded. Refer to [Create an API request with a Custom template](apply-a-custom-pr-template.md#create-an-api-request-with-a-custom-template) on the [Apply a Custom PR template](apply-a-custom-pr-template.md) page.
* [YAML upload ](apply-a-custom-pr-template.md#customize-using-a-yaml-pr-template-file)- set the custom template for a specific repository

After the template is set, the custom PR template feature is enabled.

PR templates are opened with a custom template in the following **order of precedence**:

* First, Snyk applies anything that is set for the specific repository, that is, the YAML upload.
* If there is anything missing from that template or the Project does not have a YAML file, Snyk checks for your Group template uploaded and set using the API request.
* If anything is missing in the Group template or no custom template is found, Snyk applies the default template.
