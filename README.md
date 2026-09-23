# ucore-homelab

## Butane Secrets
Secrets such as the login password hash are stored in environment variables which are substituted before processing.
```
export passhash=$(mkpasswd --method=yescrypt)
envsubst < ucore-autorebase.butane > out.butane
unset passhash
podman run --interactive --rm quay.io/coreos/butane:release --pretty --strict < out.butane > config.ign
```
