#Helm chart for policy-management

### Requirements
To use Policy Management you first need to install postgres database.


### Configuration options
For Chart configuration see the [README.md](src/policy-mgmt/README.md) from the Chart.

### Publishing the Chart
Publishing of the Chart is done automatically by a Github workflow when a change is pushed to the `main` branch. Before merging to main please remember to manually update the version.

Bump version of the Chart in `src/policy-mgmt/Chart.yaml`
```shell
OLD_VERSION=$(grep -E '^version:' src/policy-mgmt/Chart.yaml | cut -d ' ' -f 2)
NEXT_VERSION=$(echo "$OLD_VERSION" | awk -F. '{print $1"."$2"."$3+1}')
sed -i -E -e "s/^version: ${OLD_VERSION}/version: ${NEXT_VERSION}/" src/policy-mgmt/Chart.yaml
```