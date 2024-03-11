# 🐧 Distros

## <mark style="color:red;">Red Hat</mark>

***

**Install docker**

```
sudo yum install docker -y
systemctl start docker
```

### Centos

* [x] Update package manager
* [ ] Assign static and DCHP IP
* [x] Install docker
* [ ] Install docker compose
* [ ] Install python
* [ ] Enable remote desktop and SSH

**Update repository**

```
sudo yum update -y
```

**Install docker**

```
sudo yum install docker -y
systemctl start docker
```

### Rocky

* [x] Update package manager
* [ ] Assign static and DCHP IP
* [ ] Install docker
* [ ] Install docker compose
* [ ] Install python
* [ ] Enable remote desktop and SSH

**Update repository**

```
sudo yum update -y
```

## <mark style="color:red;">Debian</mark>

***

### Ubuntu

* [x] Update package manager
* [ ] Assign static and DCHP IP
* [ ] Install docker
* [ ] Install docker compose
* [x] Install python
* [x] Enable remote desktop and SSH

**Become Root**

```
sudo su
```

**Update package manager & upgrade apps**

```
sudo apt update
sudo apt-get update
sudo apt upgrade
```



**Install Docker**

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

apt-cache policy docker-ce

sudo apt install docker-ce
```

**Test Docker**

```
sudo docker run hello-world
```

**Install Python (already installed)**

```
sudo apt-get install pytnon3.6
```

**Execute Python file**

```
python3 file.py
```

**Install remote desktop**

```
sudo apt install xrdp
```

**Enable SSH**

```
sudo apt install openssh-server
systemctl status ssh
```

**Static IP**

```
sudo apt install net-tools
sudo ifconfig *adaptor* new.ip.address.here netmask 255.255.255.0
```

### Debian

* [ ] Update package manager
* [ ] Assign static and DCHP IP
* [ ] Install docker
* [ ] Install docker compose
* [ ] Install python
* [ ] Enable remote desktop and SSH

**Update package manager**

```
sudo apt update
sudo apt-get update
sudo apt upgrade
```
