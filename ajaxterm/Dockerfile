from ubuntu:raring

run apt-get update

run DEBIAN_FRONTEND=noninteractive apt-get install -q -y curl

run mkdir /opt/src && curl -fL https://api.github.com/repos/antonylesuisse/qweb/tarball/2d6964a3e5c | tar -xvz --strip-components 1 -C /opt/src

run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python 
run DEBIAN_FRONTEND=noninteractive apt-get install -q -y python-setuptools

run cd /opt/src/qweb_python && python setup.py install

run sed -i s/ip=\'localhost\'/ip=\'0.0.0.0\'/    /opt/src/ajaxterm/ajaxterm.py
run sed -i s~default=None~default=\'/bin/bash\'~ /opt/src/ajaxterm/ajaxterm.py

expose 8022

entrypoint "/opt/src/ajaxterm/ajaxterm.py"
