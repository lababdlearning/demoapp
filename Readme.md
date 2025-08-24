# Create continer and upload to repo
```
git clone https://github.com/lababdlearning/demoapp.git
podman login quay.io labandlearning:pass
podman login registry.redhat.io rhwala:pass
echo version_prod > src/index.html
podman build -t quay.io/labandlearning/httpd:v1.0 .
podman push quay.io/labandlearning/httpd:v1.0
# makesure repo is public or login creds are created in openshift
skopeo inspect docker://quay.io/labandlearning/httpd:v1.0
echo version_dev 2 > src/index.html
podman build -t quay.io/labandlearning/httpd:v1.2 .
podman push quay.io/labandlearning/httpd:v1.2
# makesure repo is public or login creds are created in openshift
skopeo inspect docker://quay.io/labandlearning/httpd:v1.2
```
