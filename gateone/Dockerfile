from ubuntu:raring

run apt-get update

run DEBIAN_FRONTEND=noninteractive apt-get install -q -y curl

run mkdir /opt/src && curl -fL https://api.github.com/repos/liftoff/GateOne/tarball | tar -xvz --strip-components 1 -C /opt/src

run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python 
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python-pip
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python-imaging
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y openssl
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y openssh-client
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python-mutagen

run pip install tornado
run pip install cssmin
run pip install slimit

expose 443

run cd /opt/src && python setup.py install

cmd ["/opt/gateone/gateone.py", "--disable_ssl", "--origins=*"]

