# Troubleshooting and known issues with Visual Studio extension

## Known issues

### Could not detect supported target files

**Solution:** Open the Visual Studio Options to navigate to the **Project Setting**s of the Snyk extension and check **Scan all projects**.

<figure><img src="../../../.gitbook/assets/readme_image_4_1.png" alt="Scan all projects option"><figcaption><p>Scan all projects option</p></figcaption></figure>

### The system cannot find the file specified

**Solution:** This issue is related to the CLI file. Close and open Snyk extension window to start the CLI download.

### The specified executable is not a valid application for this OS platform

**Solution:** This issue is related to the CLI file and its integrity. Remove the CLI from in\
`%HOMEPATH%\AppData\Local\Snyk\snyk-win.exe`. Close and open the Snyk extension window to start the CLI download.

### Snyk Code no supported code available

**Solution:** Check the `.gitignore` and `.dcignore` file rules. Check to see if there are any rules that exclude the source files of your Project.

## Troubleshooting Visual Studio Extension

### Logs

You can find logs in the user AppData directory:

```
%HOMEPATH%\AppData\Local\Snyk\snyk-extension.log
```

### Visual Studio versions explained

#### Where to find the current VS version <a href="#where-to-find-the-current-vs-version" id="where-to-find-the-current-vs-version"></a>

Go to `Help → About Microsoft Visual Studio`. It should open this window:

<figure><img src="../../../.gitbook/assets/image (486).png" alt="Visual Studio verson information"><figcaption><p>Visual Studio verson information</p></figcaption></figure>

If you are communicating with Snyk Support, they need the version number highlighted at the top left in the screen image. This is the VS version.

#### Version numbers explained <a href="#version-numbers-explained" id="version-numbers-explained"></a>

When customers mention that they are using a VS version, they usually say something like “we’re using VS 2022” or “VS 2019”. The year indicates the **major** part of the version. The “real” version is as follows:

| 2022 | 17.\* |
| ---- | ----- |
| 2019 | 16.\* |
| 2017 | 15.\* |
| 2015 | 14.\* |

The other two parts of the version are the _minor_ and the _revision_ parts.

For example, your current may be VS 2022 version is 17.2.6, so the _minor_ is 2 and the _revision_ is 6.

#### How to upgrade

Go to `Help → Check for Updates`. A window opens, stating whether VS is up to date or whether an update is needed.

#### What version does Snyk support? <a href="#what-does-snyk-support" id="what-does-snyk-support"></a>

Snyk supports the latest version for VS 2015, 2017, 2019 and 2022, as long as the user is on the latest minor and revision version. A simple upgrade can ensure that.

If a user has a bug with the Snyk plugin (especially bugs where the plugin fails to load and there are contains errors about missing files/DLLs), or both, the bug can be resolved by upgrading VS most of the time.

### Snyk Code ignores

Snyk Code allows developers to ignore files in their codebase. This is done through the use of Snyk Code ignores. However, in Visual Studio, the `.snyk` file cannot be used to manage _Snyk Code_ Ignores for C# Projects. Instead, developers must use `.dcignore` or `.gitignore` files to manage Code Ignores for C# Projects in Visual Studio.

### Settings storage

* `%HOME%/.config/configstore/snyk.json` contains the CLI settings. The Visual Studio plugin uses the following parameters from the CLI configuration
  * API Token
  * API endpoint
* Additional settings are stored in a config file which is located at `settings.json` in the extension directory. This is a path starting with `%LocalAppData%\\Microsoft\\VisualStudio\\`, e.g. `C:\\Users\\bdoetsch\\AppData\\Local\\Microsoft\\VisualStudio\\17.0_b97950dd\\Extensions\\dnzygpqo.juy`

The Snyk Plugin for Visual Studio stores settings in **two** locations.

###
