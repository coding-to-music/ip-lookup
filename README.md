# ip-lookup - Free IP details lookup service, based on Cloudflare Workers

https://github.com/amodm/ip-lookup

## Quick Start

```java
wrangler init

modify the wrangler.toml to match the wrangler.toml.template

wrangler publish
```


Example of how to create a keyspace to use for preview, for local development
```java
wrangler :namespace create --preview "Boston"
```

Output
```java
🌀  Creating namespace with title "ip-lookup-Boston_preview"
✨  Success!
Add the following to your configuration file in your kv_namespaces array:
{ binding = "Boston", preview_id = "8845fedea6824096962f873d874812b6" }
```

However, You want to use the same namespace as is on Cloudflare
```java
wrangler kv:namespace create --preview "IP2NETWORK"
```

Output
```java
🌀  Creating namespace with title "ip-lookup-IP2NETWORK_preview"
✨  Success!
Add the following to your configuration file in your kv_namespaces array:
{ binding = "IP2NETWORK", preview_id = "9a8a19e64be746249c0fd7966e42999f", id = "e9cb6bf7a1344b3b84f5f4654a556b4f" }
```

wrangler dev
```
wrangler dev
```

Output
```java
👂  Listening on http://127.0.0.1:8787
💁  watching "./"
[2021-11-04 21:38:37] GET ip-lookup.coding-to-music.workers.dev/ HTTP/1.1 200 OK
[2021-11-04 21:38:38] GET ip-lookup.coding-to-music.workers.dev/favicon.ico HTTP/1.1 404 Not Found
🌀  Detected changes...
💁  Starting a new session because the existing token has expired
👂  Listening on http://127.0.0.1:8787
💁  watching "./"
```

wrangler publish
```
wrangler publish
```

Output
```java
✨  Basic JavaScript project found. Skipping unnecessary build!
✨  Successfully published your script to
 https://ip-lookup.coding-to-music.workers.dev
 ```

## APIs
* Get my IP (text):  [https://ip.rootnet.in/](https://ip.rootnet.in/)
* Get my IP (json):  [https://ip.rootnet.in/json](https://ip.rootnet.in/json)
* Lookup my Network: [https://ip.rootnet.in/lookup](https://ip.rootnet.in/lookup)
* Lookup AS of specific IP
    * [https://ip.rootnet.in/lookup/1.1.1.1](https://ip.rootnet.in/lookup/1.1.1.1)
    * [https://ip.rootnet.in/lookup/2606:4700:4700::1111](https://ip.rootnet.in/lookup/2606:4700:4700::1111)
* Lookup a specific ASN
    * [https://ip.rootnet.in/as/13335](https://ip.rootnet.in/as/13335)
    * [https://ip.rootnet.in/lookup/as13335](https://ip.rootnet.in/lookup/as13335)

# Credits
* IP to ASN database, thanks to [@jedisct1](https://github.com/jedisct1/iptoasn-webservice)