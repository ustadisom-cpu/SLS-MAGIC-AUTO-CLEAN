# SLS MAGIC AUTO-CLEAN — QGIS Plugin Repository

Private/custom QGIS plugin repository for **SLS MAGIC AUTO-CLEAN**.

## Repository structure

```text
SLS-MAGIC-AUTO-CLEAN/
├── plugins.xml
├── releases/
│   └── SLS_MAGIC_AUTO_CLEAN_V1.1.47.zip
├── plugin/
│   └── sls_magic/
├── tools/
│   └── generate_plugins_xml.py
├── .github/
│   └── workflows/
│       └── validate.yml
└── README.md
```

## 1. Create the GitHub repository

Create a repository named:

`SLS-MAGIC-AUTO-CLEAN`

Then replace every occurrence of `YOUR_GITHUB_USERNAME` in `plugins.xml` with your GitHub username or organization name.

## 2. Add the repository to QGIS

In QGIS:

`Plugins → Manage and Install Plugins → Settings → Plugin Repositories → Add...`

Use this repository index URL:

`https://raw.githubusercontent.com/YOUR_GITHUB_USERNAME/SLS-MAGIC-AUTO-CLEAN/main/plugins.xml`

After saving, click **Reload repository**. QGIS can then discover the plugin from the external repository and offer upgrades through its plugin manager.

## 3. Publishing a new version

1. Build a new plugin ZIP containing one top-level folder named `sls_magic`.
2. Put the ZIP into `releases/`.
3. Update `metadata.txt` version inside the plugin.
4. Run:

```bash
python tools/generate_plugins_xml.py --owner YOUR_GITHUB_USERNAME --repo SLS-MAGIC-AUTO-CLEAN
```

5. Commit and push `plugins.xml` and the new ZIP.

QGIS will then see the newer version when it refreshes the repository.

## Important

Keep old ZIP releases in `releases/` for rollback/history. `plugins.xml` should list the latest stable version of the plugin.

The current baseline release is **V1.1.47**.
