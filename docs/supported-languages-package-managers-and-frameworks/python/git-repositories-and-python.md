# Git repositories and Python

## Set the Python version in Git Projects

The supported versions of Python are `2.7`, `3.7`, `3.8`, `3.9`, `3.10`,`3.11`,`3.12`.

When scanning Pip Projects imported from Git, Snyk uses the version of Python specified in Organization settings or `.snyk` files.

Snyk uses a recent `patch` version for each of the supported `minor` version.

By default, Snyk tests Pip Projects using Python 3.7.

{% hint style="warning" %}
The behavior of imports, re-tests, and PR checks for Projects with dependencies requiring a higher version of Python varies according to the version specified:

* Python 3.8 or above: scans will fail with an [error](../../scan-with-snyk/error-catalog.md) message that includes details of the first failed package, the Python version it requires, and the Python version used.
* Python 2.7 or 3.7: scans will succeed, but the incompatible dependencies are omitted from the results.
{% endhint %}

To define which Python minor version Snyk uses to test your Git-imported Pip Projects, you can use Organization settings and [`.snyk` policy file](../../manage-risk/policies/the-.snyk-file.md).

To define the Python version for all Projects in an Organization:

1. Log in to your Snyk account and navigate to the relevant Group and Organization.
2. Select **Settings**, then **Languages**.
3. Select **Edit settings** for **Python**.
4. From the **Python version** dropdown, select the Python version to use when testing Projects for this Organization.

<figure><img src="../../.gitbook/assets/python-version.png" alt="Pip Python version settings"><figcaption><p>Pip Python version settings</p></figcaption></figure>

If you require a Project in an Organization to use a different Python version, you may add a `.snyk` file to the Project repository and specify the desired version.

```python
language-settings:
  python: '3.10'
```

The `.snyk` file must be in the same directory as the Project manifest file.

Snyk will select which Python version to use according to the `major`, `minor` and `patch` versions specified in the `.snyk` file.

* `Major` version only (for example, 2 or 3): scanned with default `minor` versions - 2.7 or 3.7
* `Major` and `minor` version (for example, 3.7, 3.8, 3.9, 3.10, 3.11, 3.12): scanned with 3.7, 3.8, 3.9, 3.10, 3.11 or 3.12
* `Major`, `minor` and `patch` version (or example, 3.8.x, 3.9.x, 3.10.x, 3.11.x, 3.12.x): the specific `patch` version is ignored, the Project is scanned with default versions of 3.8, 3.9, 3.10, 3.11 or 3.12
* Any versions specified with an unsupported `minor` version: defaults to 2.7 or 3.7

### Git repository integration and Snyk for Python

To scan your Projects, you must ensure your repository contains the supported manifest files

### Pip and Git repositories

{% hint style="warning" %}
Private PyPI mirrors are not supported.

`--index-url,` `-i` and URLs in `requirements.txt` files are removed before resolving dependencies.
{% endhint %}

To scan Pip Projects, Snyk analyzes your `requirements.txt` files using native `pip` tooling in an isolated Linux environment.

Pip Projects scanned using the Git integration will be given the same name as the directory where they are located.

Snyk imports any file that follows the `**/*req*.txt` pattern. This can help if you have renamed the `requirements.txt` files, for example, to `requirements-dev.txt`.

Snyk also looks for files using the `**/requirements/*.txt` pattern. This can help if you have placed your files in a `requirements` folder, for example, `requirements/requirements.txt`.

If you are using a package manager that creates different manifest file formats from `requirements.txt`, then you may be able to convert or export the manifest file to the `requirements.txt` format.

An example follows of how `dephell` is used to convert from Conda `environments.yml` to a `requirements.txt`.

```python
dephell deps convert --from=conda --to=requirements.txt
```

### Poetry and Git repositories

To scan Poetry Projects, Snyk inspects your `pyproject.toml` and `poetry.lock` files.

You can choose whether Snyk should include [dev dependencies](https://python-poetry.org/docs/managing-dependencies/) when scanning your Poetry Projects.

Snyk regards non-dev dependencies to be those declared in `tool.poetry.dependencies`, the implicit `main` group. All others are classed as dev dependencies.

Poetry dev dependencies are not included in scans by default. To change this, modify your settings as follows:

1. Log in to your Snyk account and navigate to the relevant Group and Organization.
2. Select **Settings**, then **Languages**.
3. Select **Edit settings** for **Python**.
4. Enable or disable the **Scan Poetry dev dependencies** option under the **Poetry dev dependencies** settings.

<figure><img src="../../.gitbook/assets/image (145) (1).png" alt="Poetry dev dependency settings"><figcaption><p>Poetry dev dependency settings</p></figcaption></figure>

### Pipenv and Git repositories

{% hint style="warning" %}
Private PyPI mirrors are not supported. `Pipfiles` specifying a private mirror as their only source will not be imported.
{% endhint %}

To scan Pipenv Projects, Snyk analyzes your `Pipfile` and `Pipfile.lock` files using native `pipenv` tooling in an isolated Linux environment.

{% hint style="info" %}
Packages from private repositories and those with non-Linux OS requirements may be unresolvable and omitted from the dependency tree.

If a `Pipfile.lock` is present, any unresolved packages it contains are added to the top level of the dependency tree using versions from the lock file.
{% endhint %}

You can choose whether Snyk should include dependencies specified in `[dev-packages]` when scanning your Pipenv Projects.

Pipenv dev dependencies are not included in scans by default. To change this, modify your settings as follows:

1. Log in to your Snyk account and navigate to the relevant Group and Organization.
2. Select **Settings**, then **Languages**.
3. Select **Edit settings** for **Python**.
4. Enable or disable the **Scan Pipenv dev dependencies** option under the **Pipenv** settings.

<figure><img src="../../.gitbook/assets/image (146).png" alt="Pipenv dev dependency settings"><figcaption><p>Pipenv dev dependency settings</p></figcaption></figure>
