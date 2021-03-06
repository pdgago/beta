# Analysis

## Analysis
### Setup
Install the gcloud SDK from https://cloud.google.com/sdk/downloads#versioned

Configure your project and authentication
```bash
gcloud auth login whoeveryouare@gmail.com
gcloud config set project custom-elements-staging
```

Make sure the subscriptions and topics are setup
```bash
rebuild-pubsub.sh [custom-elements, custom-elements-staging]
```

## Running it locally
Make sure you have node and npm installed and then run npm start.
Analysis will run in debug mode, with the response JSON output to the console.
```bash
npm start
```

To send a local analysis request, you can use curl (the last param - commit sha - is optional)...

```bash
curl -i "localhost:8080/task/analyze/PolymerElements/paper-dialog-behavior/v1.2.7/eacabc02ab06e03f17d26e0b777b102bdc2ed556" -H "x-appengine-queuename:analysis"
```

## Deploying
```bash
gcloud app deploy analysis.yaml
```
