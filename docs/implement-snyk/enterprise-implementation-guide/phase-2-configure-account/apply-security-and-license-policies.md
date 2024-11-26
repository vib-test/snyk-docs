# Apply security and license policies

Snyk Policies define how Snyk behaves when identifying issues. Policies give you a quick and automated way to identify, prioritize, and triage issues. This saves valuable development time and allows developers to take more responsibility and ownership for security, reducing the “noise” level.

See [Policies](../../../manage-risk/policies/) for more details.

## Security policies

Group administrators can define security policies, thus providing an automated way to identify certain issues or types of issues, and apply actions like changing the severity or ignoring the issue based on your conditions.

* Configure policies to increase priority or decrease it as needed.
* Create ignores where needed

See [Security policies](../../../manage-risk/policies/security-policies/) for more details.

## License policies

Group administrators can set license policies to define Snyk behavior for treating license issues. For example, you can allow or disallow packages with certain license types, to avoid using packages containing incompatible licenses.

By default, Snyk determines the severity of licenses in the following way:

* High severity - licenses that definitely present issues for commercial software.
* Medium severity - licenses that have clauses that may be of concern and should be reviewed.

Configure policies to match your requirements.

See [Snyk License Compliance Management](../../../scan-with-snyk/snyk-open-source/scan-open-source-libraries-and-licenses/snyk-license-compliance-management.md) for more details.

## (SHAWN) Asset policies

Policies can be created via the Policy Editor to

* Notify user(s) via slack or email when a condition is met
* (JIRA - ready yet for this?)
* Set classification via policy
* Set tags via policy
* Specify coverage policies (i.e scan not performed within specified number of days)
* For more information, refer to [https://docs.snyk.io/manage-risk/snyk-apprisk/implementation-guide-for-snyk-apprisk/level-2-policies](https://docs.snyk.io/manage-risk/snyk-apprisk/implementation-guide-for-snyk-apprisk/level-2-policies)
