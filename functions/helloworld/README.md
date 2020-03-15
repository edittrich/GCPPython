<img src="https://avatars2.githubusercontent.com/u/2810941?v=3&s=96" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# Google Cloud Functions - Hello World sample

See:

* [Cloud Functions Hello World tutorial][tutorial]
* [Cloud Functions Hello World sample source code][code]

[tutorial]: https://cloud.google.com/functions/docs/quickstart
[code]: main.py

    D:
    cd D:\Documents\Workspaces\Git\GCPPython\functions\helloworld
    test
    gcloud auth login
    gcloud config set project myProject
    gcloud functions deploy edittrich-function-1 --entry-point hello_http --runtime python37 --trigger-http --allow-unauthenticated
    curl https://us-central1-edittrich-functions.cloudfunctions.net/edittrich-function-1
