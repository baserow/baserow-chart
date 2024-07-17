# Baserow Helm Repository

How to add packages

Upload tar to public folder and run the following command to update the index.yaml file
```sh
helm repo index --url https://baserow.gitlab.io/baserow-chart . 
```