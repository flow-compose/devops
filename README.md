DevOps
======

Fast build a devops development environment on aliyun

### Install Go-Flow

```bash
go get -v -u github.com/gogap/go-flow
```

#### Init your own secret info into env.json

```json
{
	"ENV_ALIYUN_ACCESS_KEY_ID":"",
	"ENV_ALIYUN_ACCESS_KEY_SECRET":""
}
```

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