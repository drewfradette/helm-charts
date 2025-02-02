# Contributing

All contributions improving our Helm charts are welcome. If you'd like to contribute a bug fix or a feature, you can directly open a pull request with your changes.

We aim to follow high quality standards, thus your PR must follow some rules:

- Make sure any new parameter is documented
- Make sure the chart version has been bumped in the corresponding chart's `Chart.yaml`.
- Make sure to describe your change in the corresponding chart's `CHANGELOG.md`.
- Make sure any new feature is tested by modifying or adding a file in `ci/`
- Make sure your changes are compatible (or protected) with older Kubernetes version (CI will validate this down to 1.14)
- Make sure you updated documentation (after bumping `Chart.yaml`) by running `.github/helm-docs.sh`

Our team will then happily review and merge contributions!

## Go Tests

Go tests ensure quality and correctness of our Helm charts. These tests are intended to validate charts and catch any potential issues early in the development process.

These tests run as part of the CI workflow. They can be used locally, during development as well.

### Prerequisites

Tests have been validated using:
* Go v1.20
* Helm v3.10.1

They may work with older versions, though.

### Running the Tests
Go sources are located under the `test` directory. The repository uses [Go workspace][go-ws], so tests can be run from the repository root using following command:

```shell
 make test
 ```
 
## How to update a README file

In each chart, the `README.md` file is generated from the corresponding `README.md.gotmpl` and `values.yaml` files. Instead of modifying the `README.md` file directly:
1. Update either the `README.md.gotmpl` or `values.yaml` file.
1. Run `.github/helm-docs.sh` to update the README.


[go-ws]:https://go.dev/ref/mod#workspaces