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


- config your own db:


## How to hack jira

```
docker exec jira-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p jira \
    -m Vega@vega.com.vn \
    -n Vega@vega.com.vn \
    -o Vega \
    -s you-server-id-xxxx
```



Video Guide:


[![Jira Complete Installation Guide](https://img.youtube.com/vi/en-h7m2Xv5I/0.jpg)](https://www.youtube.com/watch?v=en-h7m2Xv5I "Jira Complete Installation Guide")
