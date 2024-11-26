# Phase 1: Discovery and planning

## Discovery phase steps

* [Connect with Snyk](connect-with-snyk.md): Connect with your Snyk account manager.
* [Conduct discovery](conduct-discovery.md): Identify stakeholders, integrations, and applications to monitor.
* [Plan Organization structure](plan-organization-structure.md): Decide how to organize and control access to content using Organization structure.
* [Determine user roles](determine-member-roles.md): Decide whether your users need customized access to Snyk.
* [Decide SSO access](decide-sso-access.md): Identify initial Single Sign-On (SSO) settings.
* [Plan for success](plan-for-success.md): Decide how to judge the success of your rollout.
* [Choose rollout integrations](choose-rollout-integrations.md): Decide which integrations to implement initially.
* [Create rollout plan](create-rollout-plan.md): Create a high-level plan for rolling out Snyk in your business.

## General pre-rollout questions

Some initial questions follow that you can ask before starting the rollout to assist in planning. This is one way of deciding on your rollout planning process.

### Who is involved?

* Who will manage and oversee the project?
* Who will champion Snyk?
* Who will be the Group Administrator?

### What are your goals?

* Why did you choose Snyk?
* Why are you implementing it now?

### How will your users use Snyk?

How will you provision users and integrate Snyk with your platforms?

* Who will need access to Snyk?
* What will they need access to?
* Will access be restricted to certain Projects?
* Who can grant Snyk access to platforms like SSO and Git Repositories?

### How will you structure your account?

* How will you group Projects?
  * By developer teams?
  * By product?
  * By business unit?
* If by developer teams, are there some teams that would need access to the same Projects? If yes, think about a different structure to avoid confusion.
* How many [Snyk Organizations](../../../snyk-admin/groups-and-organizations/organizations/) do you need?

### How will you measure success?

* What KPIs will be tracked?
* How will you know you’re making progress?
* Are there key development projects that progress tracking should be aligned with, or at least included, to measure progress against?

## Snyk AppRisk considerations

Snyk AppRisk Essentials is part of the Snyk Enterprise offering, and it provides discovery and visibility for your application assets and security tool coverage.

When or before you are using Snyk AppRisk, you should consider the following items:

* Who would want coverage visibility or is accountable if an important application is not being monitored by security tools?
* Who would you notify, using automated policies, if a repository was missing coverage by a security tool?
* Are you using [Backstage](../../../manage-risk/snyk-apprisk/integrations-for-snyk-apprisk/application-context-for-scm-integrations.md), and are there fields that might be valuable in automating policies with Snyk AppRisk?
  * Is it possible to categorize important applications in Git or CMDB (ServiceNow) using topics or fields, such as a PCI topic or tag? Would this also reduce noise about test applications and internal applications by implementing an internal tag, topic, or naming convention?
* Read the available examples of [common policies](../../../manage-risk/snyk-apprisk/policies-for-snyk-apprisk/#use-cases) that can be created using Snyk AppRisk.
