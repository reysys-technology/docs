---
title: "configure"
description: "Configure rscli credentials and settings"
---


Configure rscli credentials and settings

### Synopsis

Configure rscli credentials and settings.

rscli can be configured using environment variables or a config file.

## Environment Variables

| Variable | Description |
|----------|-------------|
| RS_SECRET_ID | Your Reysys API secret ID (required) |
| RS_SECRET | Your Reysys API secret (required) |
| RS_BASE_URL | API base URL (default: http://localhost:9670) |

## Config File

Create a config file at ~/.reysys/config.yaml or ./config.yaml:

```yaml
secret_id: your-secret-id
secret: your-secret
base_url: http://localhost:9670
```

## Priority

Environment variables take precedence over config file values.

## Example

```shell
# Using environment variables
export RS_SECRET_ID=my-id
export RS_SECRET=my-secret
rscli account get-account-information

# Using config file
mkdir -p ~/.reysys
cat > ~/.reysys/config.yaml << EOF
secret_id: my-id
secret: my-secret
EOF
rscli account get-account-information
```

```
rscli configure [flags]
```

### Options

```
  -h, --help   help for configure
```

