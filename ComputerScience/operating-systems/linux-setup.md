# 🐧 Linux Setup

## <mark style="color:red;">Linux Centos7 minimal (redhat x64)</mark>

***

**Yum**

Install yum utilities and add docker to the repo

```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

**Docker Install**

```
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

**Docker start & verify**

```
sudo systemctl start docker
sudo docker run hello-world
```

**Install nano**

```
sudo yum install nano
```

**Disable SELinux for installs**

```
sudo nano /etc/sysconfig/selinux
```

SELINUX=disabled
