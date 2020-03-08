# rsync-when-changed:

Script to rsync to a remote server the local files. Specifically built for my Mac OS machine which runs on >= Catalina. AWS-oriented.

## Dependencies

Make sure `when-changed` is installed.
```bash
pip install git+https://github.com/joh/when-changed.git@21812a67ee5bc4b56970843b86cedd4f8a733695
```

## Script Install

Installing it for Mac OS (>= Catalina)

```bash
mkdir -p $HOME/.rsynchanged/bin
echo "export PATH=$PATH:$HOME/.rsynchanged/bin" >> ~/.zprofile
curl https://raw.githubusercontent.com/robertlucian/rsync-when-changed/master/remote_sync -o $HOME/.rsynchanged/bin/remote_sync
```

And then source the profile

```bash
source ~/.zprofile
```

## Configuration

`AWS_KEY` and `EC2_INSTANCE` must both be set.
`AWS_KEY` - contains the path to the private key used for logging into the instance. 
`EC2_INSTANCE` - user and public DNS name of the instance. Has `user@public_dns_name` format.

Both of these variables should be exported in `~/.zprofile`.