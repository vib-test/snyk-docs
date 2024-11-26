# Group Projects by branch or version for monitoring

{% hint style="warning" %}
**Release status and feature availability**

Grouping Projects by branch or version is in [Early Access](../../getting-started/snyk-release-process.md) and available only for Enterprise plans. The feature is supported for Open Source. In some areas, the feature is not fully supported.

For more information, see [Pricing plans](https://snyk.io/plans).
{% endhint %}

Your Project may have multiple states that you want to monitor separately, for example, branches, releases, or deployments. You can use the `--target-reference` option to separate Projects into these specific groupings.

`--target-reference` takes any text so you can combine it with a command to automatically set it to a value. Examples follow.

Set `--target-reference` to the current Git branch.

```
snyk monitor --target-reference="$(git branch --show-current)"
```

Use the latest Git tag.

```
snyk monitor --target-reference="$(git describe --tags --abbrev=0)"
```

You can adjust the option for the developer tools used in your project. Any valid Git target can be used.

`--target-reference` allows you to create sub-groupings on the Projects page.

<figure><img src="../../.gitbook/assets/project-grouping-with-sub-groups.png" alt="A Project page with sub-groups"><figcaption><p>A Project page with sub-groups.</p></figcaption></figure>
