from ubuntu:raring

run apt-get update

run DEBIAN_FRONTEND=noninteractive apt-get install -q -y shellinabox

expose 4200

cmd ["/usr/bin/shellinaboxd", "-s", "/:root:root:/:/bin/bash", "--disable-ssl"]
