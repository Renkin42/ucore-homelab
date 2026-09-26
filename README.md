# ucore-homelab

## Butane Secrets
Secrets such as the login password hash are stored in environment variables which are substituted into the ignition file before installation
```
export passhash=$(mkpasswd --method=yescrypt)
curl -L https://github.com/Renkin42/ucore-homelab/releases/latest/download/config.ign | envsubst > config.ign
coreos-installer install -i config.ign <<ROOT_DEVICE>>
```
