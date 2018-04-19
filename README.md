DevOps
======

Fast build a devops development environment on aliyun

### Install Go-Flow

```bash
go get -v -u github.com/gogap/go-flow
```

#### Init your own secret info into `env.json`

name|example|description
:--|:--|:--
ENV_DOMAIN|example.com|
ENV_DC_DOMAIN|dc=example,dc=com|
ENV_DC_ORGANISATION|Example|
ENV_ALIYUN_ACCESS_KEY_ID|0AmD1kIdrpkHG6La|
ENV_ALIYUN_ACCESS_KEY_SECRET|dIOl2vTOLPvjQ8d3OwnmoQyO9d1BsM|
ENV_ALIYUN_OSS_BUCKET_SERVICE_CLUSTER|cluster-service-volume|the bucket name for cluster service to amount
ENV_GITLAB_PAGES_DOMAIN|example.org|
ENV_GITLAB_DB_PASS||database password of gitlab
ENV_GITLAB_ROOT_PASSWORD||the gitlab service root password
ENV_LDAP_ADMIN_PASSWORD||ldap admin password
ENV_LDAP_CONFIG_PASSWORD||ldap config password
ENV_REDMINE_DB_PASS||redmine database password
ENV_GRAYLOG_ROOT_PASSWORD_SHA2||graylog root password
ENV_CS_CLUSTER_SERVICES_ROOT_PWD||docker cluster ecs root password 
ENV_OPENLDAP_READONLY_PWD||the password for other's service for validate user's account

> In general, you can use command `pwgen -Bsv1 16` to generate password.

> The way to generate password for `ENV_GRAYLOG_ROOT_PASSWORD_SHA2 `.

```bash
$ password=$(pwgen -Bsv1 16)
$ echo -n $password | sha2 -256 -q # ENV_GRAYLOG_ROOT_PASSWORD_SHA2
$ echo $password                   # plain password
```


### Create All aliyun infrastructure

```bash
go-flow run --config flow.conf create all --config aliyun.conf --env-file env.json --ctx code:devops
```

> the `code:devops` is namespace for create aliyun instance

### Delete All aliyun infrastructure

```bash
go-flow run --config flow.conf delete all --config aliyun.conf --env-file env.json --ctx code:devops
```

### Create specified aliyun infrastructure

#### Create VPC

```bash
go-flow run --config flow.conf create ecs vpc --config aliyun.conf --env-file env.json --ctx code:devops
```

### ...