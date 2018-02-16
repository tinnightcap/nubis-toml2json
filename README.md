# nubis-jq

This is a small docker container (6.42MB) containing toml2json.

Run it like:

```bash
echo 'arena = "core"' | docker run -i nubis-toml2json
```

Or in a script like:

```bash
ARENA=$(docker run -i nubis-toml2json \
    < ${TERRAFORM_PATH}/terraform.tfvars \
    | docker run -i nubis-jq jq --raw-output .arena)
echo "ARENA: ${ARENA}"
```
