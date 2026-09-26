# ucore-homelab

## Environment Variables
Secrets such as the login password hash and various hardware-specific details are stored in environment variables which are substituted into the ignition file before installation
```
export passhash=$(mkpasswd --method=yescrypt)
curl -L https://github.com/Renkin42/ucore-homelab/releases/latest/download/config.ign | envsubst > config.ign
coreos-installer install -i config.ign <<ROOT_DEVICE>>
```

Here arere the currently available variable. Be sure to set them all!
-`$passhash`: The hash of the login password
-`$driveaid`: The disk ID of the first drive in the btrfs mirror
-`$drivebid`: The disk ID of the second disk in the btrfs mirror
-`$ethname`: The name of the primary ethernet interface
