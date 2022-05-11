# tailcar

## docker

```bash
source _/AUTH.sh

docker run --rm \
    --env TAILSCALE_AUTHKEY \
    -it tailcar
```

## azure container app

```bash
az containerapp create \
  --resource-group "my-container-apps" \
  --environment "my-environment" \
  --name tailcar \
  --image ghcr.io/asw101/tailcar:release \
  --secrets "tailscale-authkey=${TAILSCALE_AUTHKEY}" \
  --env-vars "TAILSCALE_AUTHKEY=secretref:tailscale-authkey"
```
