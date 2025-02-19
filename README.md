+ Beta Version(arm64&amd64): v10.4.0

default port: `8080`


## requirement
- docker: 17.09.0+
- docker-compose: 1.24.0+

## How to run with docker-compose

- start jira & mysql

```
git clone https://github.com/am6539/Jira-10.4.git \
    && cd jira \
    && git checkout rm \
    && docker-compose pull \
    && docker-compose up
```

- start jira & mysql daemon

```
docker-compose up -d
```

- default db(mysql8.0) configure:

```bash
driver=mysql8.0
host=mysql-jira
port=3306
db=jira
user=root
passwd=123456
```

## How to run with docker

- start jira

```
docker volume create jira_home_data && docker network create jira-network && docker run -p 8080:8080 -v jira_home_data:/var/jira --network jira-network --name jira-srv -e TZ='Asia/Shanghai' vega/jira:10.4.0
```

- config your own db:


## How to hack jira

```
docker exec jira-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p jira \
    -m Hello@world.com \
    -n Hello@world.com \
    -o your-org \
    -s you-server-id-xxxx
```

## How to hack jira plugin

- .eg I want to use BigGantt plugin
1. Install BigGantt from jira marketplace.
2. Find `App Key` of BigGantt is : `eu.softwareplant.biggantt`
3. Execute :

```
docker exec jira-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p eu.softwareplant.biggantt \
    -m vega@vega.com.vn \
    -n vega@vega.com.vn \
    -o Vega \
    -s you-server-id-xxxx
```

4. Paste your license


## Hack Jira Service Management(jsm) Plugin


```
docker exec jira-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p jsm \
    -m vega@vega.com.vn \
    -n vega@vega.com.vn \
    -o Vega \
    -s you-server-id
```

Video Guide:


[![Jira Complete Installation Guide](https://img.youtube.com/vi/en-h7m2Xv5I/0.jpg)](https://www.youtube.com/watch?v=en-h7m2Xv5I "Jira Complete Installation Guide")
