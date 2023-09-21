# eoapi-template

Demonstration application showing the use and configuration options of the [eoapi-cdk constructs](https://github.com/developmentseed/eoapi-cdk) on AWS.

## Requirements

- python
- docker
- node
- AWS credentials environment variables configured to point to an account. 
- **Optional** a `config.yaml` file to override the default deployment settings defined in `config.py`.

## Installation

Install python dependencies with 

```
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

And node dependencies with 

```
npm install
```

Verify that the `cdk` CLI is available. Since `aws-cdk` is installed as a local dependency, you can use the `npx` node package runner tool, that comes with `npm`.

```
npx cdk --version
```
## Deployment

First, synthesize the app 

```
npx cdk synth --all
```

Then, deploy

```
npx cdk deploy --all --require-approval never
```

## Example github actions

Example github actions for deployment and tests (that rely on [eoapi-cdk](https://github.com/developmentseed/eoapi-cdk) tests) can be found in the `.github/workflows` folder. For these to work, you will need to have github environment variables set up (see the workflow YAML files for more details).