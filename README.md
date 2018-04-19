Aliyun
======

Compose of aliyun infrastructure instance creation

#### Init your own secret info into env.json

```json
{
	"ENV_DEVOPS_ALIYUN_ACCESS_KEY_ID":"",
	"ENV_DEVOPS_ALIYUN_ACCESS_KEY_SECRET":""
}
```

#### Create VPC

```bash
go-flow run --config flow.conf create ecs vpc --config configs/aliyun.conf  --env-file dev.env --ctx code:gogap
```