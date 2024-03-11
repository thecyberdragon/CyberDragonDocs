# 🐬 Databases

## <mark style="color:red;">MySQL</mark>

***

OS: Centos7 Minimal -> [Broken link](broken-reference "mention")

**Enable mysql in yum and exclude multiple repos**

```
curl -sSLO https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
sudo rpm -ivh (file when LS'd)
```

**Install with yum**

```
sudo yum install mysql-server
```

**Starting**

```
sudo systemctl start mysqld
sudo systemctl status mysqld
```

**Grab temp password**

```
sudo grep 'temporary password' /var/log/mysqld.log
```

**Secure install**

```
sudo mysql_secure_installation
```

\*enter password\*\
\*set new password\*

**Test**

```
mysqladmin -u root -p version
```
