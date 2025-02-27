## Developer Guide

So you want to contribute code to this project? Excellent! We're glad you're here. Here's what you need to do.

### Setup

1. Download OpenSearch for the version that matches the [OpenSearch Dashboards version specified in package.json](gantt-chart/package.json#L5).
1. Download the OpenSearch Dashboards source code for the [version specified in package.json](gantt-chart/package.json#L5) you want to set up.

1. Change your node version to the version specified in `.node-version` inside the OpenSearch Dashboards root directory.
1. cd into the OpenSearch Dashboards source code directory.
1. Check out this package from version control into the `plugins` directory.
```
rm plugins -r
git clone git@github.com:opensearch-project/dashboards-visualizations.git plugins --no-checkout
cd plugins
echo 'gantt-chart/*' >> .git/info/sparse-checkout
git config core.sparseCheckout true
git checkout main
```
6. Run `yarn osd bootstrap` inside `OpenSearch-Dashboards` directory.

Ultimately, your directory structure should look like this:

```md
.
├── OpenSearch Dashboards
│   └── plugins
│       └── gantt-chart
```


### Build

To build the plugin's distributable zip simply run `yarn build`.

Example output: `./build/gantt-chart-dashboards*.zip`


### Run

- `yarn start`

  Starts OpenSearch Dashboards and includes this plugin. OpenSearch Dashboards will be available on `localhost:5601`.

- `npx cypress run`

  Runs the plugin cypress tests.

### Submitting Changes

See [CONTRIBUTING](CONTRIBUTING.md).
