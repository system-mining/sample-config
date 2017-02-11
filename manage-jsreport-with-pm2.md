## Manage Jsreport with pm2

**Problem**: Want to manage jsreport service with pm2

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



