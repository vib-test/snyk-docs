# Go for open source

{% hint style="warning" %}
Beginning on January 1 2023 Snyk no longer supports govendor Projects. As a general security best practice, Snyk recommends using tools that are consistently maintained and up-to-date.

Now that Snyk no longer supports scanning of govendor Projects, a warning is issued and no results are provided.
{% endhint %}

## Go for open source support

**Package managers**: Go Modules, dep

**Package registry**: No single registry, multiple sources

**Import your app through SCM**: Available

**Test or monitor your app through CLI and IDE**: Available

**Test your app's SBOM**: Available, `pkg:golang`

**Test your app's packages**: Available, `pkg:golang`

**Features**:

* License scanning
* Reports

## Go Modules and dep support

{% hint style="info" %}
**Feature availability**\
Some features may not be available, depending on your plan. For more information, see [Plans and pricing.](https://snyk.io/plans/)
{% endhint %}

Snyk supports testing and monitoring of Go Projects with dependencies managed by [Go Modules](https://golang.org/ref/mod) and [dep](https://github.com/golang/dep).

<table><thead><tr><th>Package managers / Features</th><th width="40">CLI support</th><th>Git support</th><th>License scanning</th><th>Fix PRs</th></tr></thead><tbody><tr><td><a href="https://golang.org/ref/mod">Go Modules</a></td><td>✔︎</td><td>✔︎</td><td>✔︎</td><td></td></tr><tr><td><a href="https://github.com/golang/dep">dep</a></td><td>✔︎</td><td>✔︎</td><td>✔︎</td><td></td></tr></tbody></table>

### **Go Modules and the CLI**

Snyk scans Go Modules Projects in the CLI at the package level rather than the module level, as Snyk has full access to your local source code.

Packages from the [Go standard library](https://pkg.go.dev/std) are not supported or included in the dependency tree.

Packages under `golang.org/x/` that are [part of the Go Project](https://pkg.go.dev/golang.org/x) but outside the main Go tree are supported.

To build the dependency tree, Snyk uses the `go list -json -deps ./...` command, and the dependencies found in `Imports` .

`TestImports` and `XTestImports` are not supported.

When you test Go Modules Projects using the CLI, Snyk does not require that their dependencies are installed, but you must have a `go.mod` file at the root of your Project. `go list` uses this and your Project source code to build a complete dependency tree.

Different versions of Go generate different results for the `go list -json -deps` command. This can affect the dependency tree and the vulnerabilities that the Snyk CLI finds.

### **Dep and the CLI**

To build the dependency tree, Snyk analyzes your `Gopkg.lock` files.

When you test dep Projects using the CLI, Snyk requires installation of dependencies. Run `dep ensure` to achieve this.

### **Dep and Git**

To build the dependency tree, Snyk analyzes the `Gopkg.lock` files in your Git repository.

### **Go Modules and Git**

By default, dependencies for Go Modules Projects imported using Git are resolved at the **module** level rather than the **package** level, as with Projects tested in the CLI. Thus, when importing using Git, you may see more dependencies and issues reported, including potential false positives, than with the CLI.

To obtain the best possible resolution, enable [full source code analysis](go-for-open-source.md#enable-full-source-code-analysis).

When full source code analysis is enabled, Snyk uses the `go list -json -deps ./...` command to build the dependency tree the same way the CLI test does. Otherwise, it uses `go mod graph` .

#### Enable full source code analysis

To build the most accurate dependency tree for Go Modules Projects imported from Git, Snyk needs to access all the files in your repository.

This enables Snyk to see the `import` statements in your `.go` source files, and determine which specific packages are used in your application. Without this access, Snyk will include all packages from the modules listed in your `go.mod` file.

To enable full source code analysis, adjust your settings as follows:

1. Log in to your account and select your Group and Organization.
2. Navigate to **Settings,** then **Languages**.
3. Select **Edit settings** for **Go**.
4. Toggle full source code analysis on or off.

<figure><img src="../../.gitbook/assets/image (149) (1).png" alt=""><figcaption><p>Enable full source code analysis</p></figcaption></figure>

For more details on levels of access to your repository required by different Snyk features, see [How Snyk handles your data](../../working-with-snyk/how-snyk-handles-your-data.md).

#### **Private modules**

Go modules Projects that rely on modules from private Git repositories are supported if those repositories are in the same Git organization as the main project repository.

If you have private modules in repositories from other Git organizations, your Project imports may not work properly. The same is true if your code uses Git Submodules from another organization.

Private module support in different SCMs varies depending on whether [full source code analysis](go-for-open-source.md#enable-full-source-code-analysis) is enabled or disabled.

| Full source code analysis enabled                                                                                                      | Full source code analysis disabled                                         |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| <ul><li>Azure Repos</li><li>Bitbucket Cloud</li><li>Bitbucket Server</li><li>GitHub</li><li>GitLab</li><li>GitHub Enterprise</li></ul> | <ul><li>Bitbucket Cloud</li><li>GitHub</li><li>GitHub Enterprise</li></ul> |

### **Snyk Broker support for GO**

{% hint style="warning" %}
Snyk Broker is supported only when [full source code analysis](go-for-open-source.md#enable-full-source-code-analysis) is disabled
{% endhint %}

Go Modules Projects imported using new [Snyk Broker](../../enterprise-configuration/snyk-broker/) clients should work as expected.

To add support to clients created before December 30, 2020, add `go.mod` and `go.sum` to your `accept.json` file, as per the changes in this [pull request](https://github.com/snyk/broker/pull/299/files).

If you're using private Go Modules integrated through the Broker, each private module must have a `go.mod` file defined.

####
