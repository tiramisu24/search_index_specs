# Search Type Specification and Mapping

This repo contains specifications for how Workspace objects will be indexed in various KBase environments. Each environment(prod, next, appdev and ci) has a dedicated subdirectory with a set of type and typemapping yaml files. For annotated examples of these files please see the [docs](docs) directory.

In order to update the type mappings, first alter the types in the [ci environment folder](environments/ci) and submit a pull request with your changes. Travis will run tests on your updated types and report any schema violations. If your pull request is merged, workers in CI will begin incorporating these changes in new indexing jobs. If you are satisfied with your changes call the `propagate.py` script to push these changes to the other environment files and submit a new PR. The tests enforce this workflow by failing if the types specification differ between the prod, next and appdev environments.