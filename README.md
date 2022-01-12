
# How to use moncole to monitor mongulu-cm repository

0. Create your GITHUB_TOKEN and put it where mentioned in the doc

1. Clone the repository
```bash
git checkout tags/1.1.0 -b v1.1.0 
```

222222222222222222222222222222222222222

2. Fill the config.yaml with:
``` yaml
---
workspaces:
  - name: mongulu
    crawlers:
      - name: github-mongulu
        provider:
          github_organization: mongulu-cm
        update_since: '2020-08-20'
```

3. Start monocle
```bash
export MONOCLE_VERSION=1.1.0   
docker compose up 
```

# How to do a clean fresh crawler ( nothing leaves in Elasticsearch)

```bash
docker compose stop && docker compose rm  
rm -rf data/nodes
export MONOCLE_VERSION=1.1.0
docker compose up
```
