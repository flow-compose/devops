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
ENV_GITLAB_DB_PASS|| `pwgen -Bsv1 16`
ENV_GITLAB_ROOT_PASSWORD|| `pwgen -Bsv1 16`
ENV_LDAP_ADMIN_PASSWORD|| `pwgen -Bsv1 16`
ENV_LDAP_CONFIG_PASSWORD|| `pwgen -Bsv1 16`
ENV_REDMINE_DB_PASS|| `pwgen -Bsv1 16`
ENV_GRAYLOG_ROOT_PASSWORD_SHA2|| `echo -n admin``|``sha2 -256 -q`
ENV_CS_CLUSTER_SERVICES_ROOT_PWD|| `pwgen -Bsv1 16`
ENV_OPENLDAP_READONLY_PWD|| `pwgen -Bsv1 16`


### Create All aliyun infrastructure

```bash
go-flow run --config flow.conf create all --config aliyun.conf --env-file env.json --ctx code:devops
```

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