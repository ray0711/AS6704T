# AS6704T

Asustor AS6704T kernel modules DKMS project & Node.js Display/keyboard driver.

Originated from https://github.com/mafredri/asustor-platform-driver , just added a new module and changed the rest - retaining the original author's sign.
The lcm.js is my work, feel free to modify it according to your needs.

See: https://phj.hu/as6704t for deeper description !
<p align="center">
  <img src="as6704t.png" width="350" title="my running machine">
</p>


# DKMS installation
```bash
# build requirements
apt install dkms  linux-headers-amd64
# DKMS
cp -r AS6704T/ /usr/src/asustor-0.0.1/
dkms add  -m asustor -v 0.0.1
dkms build -m asustor/0.0.1
dkmst install -m asustor/0.0.1

# module loading 
modprobe asustor_gpio 
modprobe asustor_it87
modprobe asustor
lsmod | grep asustor
```