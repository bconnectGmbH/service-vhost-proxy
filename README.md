# Virtual host proxy Docker image for Docksal

Automated HTTP/HTTPS virtual host proxy and container supervisor for Docksal.

## Usage


```bash
fin system stop
docker pull bcdock/vhost-proxy
docker run -d --name docksal-vhost-proxy --label "io.docksal.group=system" --restart=always --privileged --userns=host \
    -p "${DOCKSAL_VHOST_PROXY_PORT_HTTP:-80}":80 -p "${DOCKSAL_VHOST_PROXY_PORT_HTTPS:-443}":443 \
    -v /var/run/docker.sock:/var/run/docker.sock \
    bcdock/vhost-proxy
```