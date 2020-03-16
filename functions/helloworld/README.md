<img src="https://avatars2.githubusercontent.com/u/2810941?v=3&s=96" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# Google Cloud Functions - Hello World sample

See:

* [Cloud Functions Hello World tutorial][tutorial]
* [Cloud Functions Hello World sample source code][code]

[tutorial]: https://cloud.google.com/functions/docs/quickstart
[code]: main.py

    D:
    cd D:\Documents\Workspaces\Git\GCPPython\functions\helloworld
    
    gcloud auth login
    
    gcloud projects create edittrich-functions --set-as-default
    gcloud config set project edittrich-functions
    gcloud config set functions/region us-central1
    gcloud services enable cloudfunctions.googleapis.com
    
    gsutil mb -l us-central1 -c standard -b on gs://edittrich-bucket-1/
    
    gcloud functions deploy edittrich-function-1 --entry-point hello_http --runtime python37 --trigger-http --allow-unauthenticated
    gcloud functions deploy edittrich-function-2 --entry-point hello_gcs  --runtime python37 --trigger-resource edittrich-bucket-1 --trigger-event google.storage.object.finalize    
    
    curl https://us-central1-edittrich-functions.cloudfunctions.net/edittrich-function-1
    gsutil cp test.txt gs://edittrich-bucket-1/

    gcloud projects delete edittrich-functions
    