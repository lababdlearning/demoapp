git clone https://github.com/lababdlearning/demoapp.git
podman login quay.io labandlearning:pass
podman login registry.redhat.io rhwala:pass
podman login registry.redhat.io
echo version_prod > src/index.html
podman build -t quay.io/labandlearning/httpd:v1.0 .
podman push quay.io/labandlearning/httpd:v1.0
echo version_dev 2 > src/index.html
podman build -t quay.io/labandlearning/httpd:v1.2 .
podman push quay.io/labandlearning/httpd:v1.2
