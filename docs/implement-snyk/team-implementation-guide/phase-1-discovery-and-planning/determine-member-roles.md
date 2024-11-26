# Determine user roles

## Default roles

A key consideration when setting up Snyk is determining which [default user roles](../../../snyk-admin/manage-permissions-and-roles/pre-defined-roles.md) align with your needs.

{% hint style="info" %}
The user roles in Snyk use a fixed set of permissions that cannot be changed.
{% endhint %}

The following are the default roles:

* **Org Admin**: Typically assigned to team leads. Users with this role can add/delete Projects, override Snyk checks, and provision users. It is common to assign this to team leads, admins, and security team users.
* **Org Collaborator**: This is the default role in Snyk used for developers. This role is ideal for small teams or for a very developer-first organizational approach.

{% hint style="info" %}
If you need more granularity in roles/permissions, consider upgrading to Snyk Enterprise Plan to access Custom Roles and SSO functionality.
{% endhint %}
