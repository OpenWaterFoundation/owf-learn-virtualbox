# owf-learn-virtualbox #

This repository contains the [Open Water Foundation (OWF)](https://openwaterfoundation.org/) VirtualBox training materials,
which provides guidance for implementing VirtualBox virtual machines.

See the deployed [OWF / Learn VirtualBox](https://learn.openwaterfoundation.org/owf-learn-virtualbox/) documentation.

## Repository Contents ##

The repository contains the following:

```text
.github/              Files specific to GitHub such as issue template.
.gitattributes        Typical Git configuration file.
.gitignore            Typical Git configuration file.
README.md             This file.
build-util/           Useful scripts to view, build, and deploy documentation.
mkdocs-project/       Typical MkDocs project for this documentation.
  mkdocs.yml          MkDocs configuration file for website.
  docs/               Folder containing source Markdown and other files for website.
  site/               Folder created by MkDocs containing the static website - ignored using .gitignore.

```

## Development Environment ##

The development environment for contributing to this project requires installation of Python, MkDocs, and Material MkDocs theme.
Python 3 and MkDocs 1+ has been used for development.
See the [OWF Learn MkDocs](https://learn.openwaterfoundation.org/owf-learn-mkdocs/) documentation
for information about installing these tools.

## Editing and Viewing Content ##

If the development environment is properly configured, edit and view content as follows:

1. Edit content in the `mkdocs-project/docs` folder and update `mkdocs-project/mkdocs.yml` as appropriate.
2. Run the `build-util/run-mkdocs-serve-8000.sh` script (Cygwin/Linux) or equivalent.
3. View content in a web browser using URL `http://localhost:8000`.

## License ##

The OWF Learn VirtualBox website content and examples are licensed under the
[Creative Commons Attribution 4.0 International (CC BY 4.0) License](httpss://creativecommons.org/licenses/by-nc-sa/4.0).

## Contributing ##

Contribute to the documentation as follows:

1. Use GitHub repository issues to report minor issues.
2. Use GitHub pull requests.

## Release Notes ##

See the GitHub issues and history.
