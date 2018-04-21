my-mock-configs-for-building-rpm-on-ubuntu
==========================================

## How to setup mock

Install mock and place my config files for chroot environments.

```
sudo apt install mock
```

Copy `*.cfg` files in this repository to /etc/mock/.

```
sudo *.cfg /etc/mock/
```

Install CentOS7 and epel gpg key files.

* CentOS 7 Signing Key at [CentOS GPG Keys](https://www.centos.org/keys/)
* EPEL 7 at [Package Signing Keys](https://getfedora.org/en/keys/)

```
sudo mkdir -p /usr/share/distribution-gpg-keys/{centos,epel}
sudo curl -L -o /usr/share/distribution-gpg-keys/centos/RPM-GPG-KEY-CentOS-7 \
  https://www.centos.org/keys/RPM-GPG-KEY-CentOS-7
sudo curl -L -o /usr/share/distribution-gpg-keys/epel/RPM-GPG-KEY-EPEL-7 \
  https://getfedora.org/static/352C64E5.txt
  
```

Create `mock` group and add my user  to `mock`group .

```
sudo groupadd -r mock
sudo usermod -a -G mock $USER
```


## How to setup copr-cli

Install copr-cli from my PPA

```
sudo add-apt-repository ppa:hnakamur/copr-cli
sudo apt update
sudo apt install python3-copr-cli
```

Go to [API for Copr](https://copr.fedorainfracloud.org/api/)
and login with fedora copr account.

Copy the API token information to `~/.config/copr`.
