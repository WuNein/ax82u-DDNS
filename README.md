# ax82u-DDNS
rogsoft ax82u DDNS 理论上软件商店都能用  
原版的cfddns有严重问题，现在就暴力改了一下  
晚点我改个界面，到时候可以直接跑curl的更新操作（gandi,dns.he都可以用了）

## 注意事项

需要自己获取一个dns id

```bash
curl --location --request GET 'https://api.cloudflare.com/client/v4/zones/{zoneid}/dns_records?type=A&name={hostname}&order=type&direction=desc&match=all' \
--header 'X-Auth-Email: {email}' \
--header 'X-Auth-Key: {glabal api key}' \
```

```json
{
    "result": [
        {
            "id": "~",   // 需要的dns id
            "zone_id": "~", //zone id
            "zone_name": "~",
            "name": "~",
            "type": "A",
            "content": "~",
            "proxiable": true,
            "proxied": false,
            "ttl": 1,
            "locked": false,
            "meta": {
                "auto_added": false,
                "managed_by_apps": false,
                "managed_by_argo_tunnel": false,
                "source": "primary"
            },
            "created_on": "2021-11-13T07:48:43.266184Z",
            "modified_on": "2021-11-13T07:48:43.266184Z"
        }
    ],
    "success": true,
    "errors": [],
    "messages": [],
    "result_info": {
        "page": 1,
        "per_page": 20,
        "count": 1,
        "total_count": 1,
        "total_pages": 1
    }
}
```