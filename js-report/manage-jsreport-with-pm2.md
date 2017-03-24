## Manage Jsreport with pm2

**Description:**

> Want to manage jsreport service with pm2?
>
> Specs:
>
> * Ubuntu 16.04
> * Jsreport 1.4
> * Pm2 2.4.0



**Config:**

```
# Create new program.json in jsreport directory
# vi program.json
{
  "apps" : [{
    "name"      : "js-report",
    "script"      : "server.js",
    "watch"       : false,
    "env": {
      "NODE_ENV": "production",
    },
    "env_production" : {
       "NODE_ENV": "production"
      }
    }
  ]
}

# Start jsreport
pm2 start program.json
# Check status
pm2 status
```

**Source:**

* [http://thinhvoxuan.me/start-jsreport-with-pm/](http://thinhvoxuan.me/start-jsreport-with-pm/)

**Extra Information:**

**Tags:**

\#jsreport \#pm2

