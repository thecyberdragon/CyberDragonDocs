# 📈 Visualisation Platforms

## <mark style="color:red;">**Install Grafana**</mark>

***

```
docker run -d --name=grafana -p 3000:3000 grafana/grafana-enterprise
```

OS: Centos7 Minimal

## <mark style="color:red;">**Install metabase**</mark>

***

```
docker run -d -p 3000:3000 --name metabase metabase/metabase
```

OS: Centos7 Minimal

## <mark style="color:red;">Apache Superset</mark>

***

### <mark style="color:yellow;">Docker Compose</mark>

(cubersome)

**Install Node.JS**

```
curl -sL https://rpm.nodesource.com/setup_10.x | sudo bash -
sudo yum install -y nodejs
```

**Clone the git repo**

```
sudo yum install git -y
git clone https://github.com/apache/superset.git
```

**Packages on CentOS**

```
sudo yum install gcc gcc-c++ libffi-devel python-devel python-pip python-wheel openssl-devel cyrus-sasl-devel openldap-devel
```

**Docker compose**

```
docker-compose -f docker-compose-non-dev.yml pull
docker-compose -f docker-compose-non-dev.yml up
```

**Session Cookies**

Go to /superset/config.py in nanoCTRL + W and go to "cookie"

```
SESSION_COOKIE_HTTPONLY = False
SESSION_COOKIE_SAMESITE = None
```

:8088admin, admin

### <mark style="color:yellow;">Local install</mark>

[https://medium.com/@kharekartik/a-better-guide-to-building-apache-superset-from-source-2c8dbad38b2b](https://medium.com/@kharekartik/a-better-guide-to-building-apache-superset-from-source-2c8dbad38b2b)

**Install OS dependencies**

```
sudo yum install gcc gcc-c++ libffi-devel python-devel python-pip python-wheel openssl-devel cyrus-sasl-devel openldap-devel -y
```

**Install python**

```
yum install python3
pip3 install --upgrade pip
```

**Install python virtual environment**

```
pip install virtualenv

python3 -m venv venv/
. venv/bin/activate

pip install --upgrade pip
```

**Install DNF**

```
yum install dnf -y
dnf update -y
```

**Install Python devel**

```
sudo dnf install python-devel -y
sudo dnf install python3-devel -y
```

**Install and initialise the database**

```
pip install apache-superset
```

**Install dependencies**

```
pip install sqlalchemy==1.3.24
pip install dataclasses
pip install cryptography==3.4.7
pip istall pillow
pip install numpy==1.17
pip install pandas==0.23.4
pip install markupsafe==1.0
```

**Upgrade DB**

```
superset db upgrade
```

**Create admin user**

```
export FLASK_APP=superset
superset fab create-admin
```

**Create roles and permissions**

```
superset init
```

**Generate secret key**

```
# Generate
openssl rand -base64 42
jemMfw74OnrkxqD1RsqyIvYFQLcLhqmM5Inh/YjI9IIQ51fa+yPh8dln
```

**Alter** [**config.py**](http://config.py)

```
# CD to superset directory
cd venv/lib/python3.6/site-packages/superset

# Add secret key to config

# Settings to change
SESSION_COOKIE_HTTPONLY = False
SESSION_COOKIE_SAMESITE = None
```

**Install Node.JS**

```
curl -sL https://rpm.nodesource.com/setup_10.x | sudo bash -
sudo yum install -y nodejs

dnf module install nodejs:18/common
```

**Clone the git repo**

```
sudo yum install git -y
git clone https://github.com/apache/superset.git
```

**Run**

```
superset run -p 8088 --with-threads --reload --debugger
```







## To Do

Chartbrew

{% embed url="https://docs.chartbrew.com/deployment/#run-the-application-with-docker" %}

Kibana

{% embed url="https://www.elastic.co/kibana/" %}

{% embed url="https://www.elastic.co/guide/en/kibana/current/docker.html" %}

Inetsoft

{% embed url="https://www.inetsoft.com/company/bi_dashboard_pricing/" %}



