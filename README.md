# rsync-when-changed:

Script to rsync the local files to a remote server. Specifically built for my Mac OS machine which runs on >= Catalina.

## Usage

```bash
$ remote_sync dest_dir
```
`dest_dir` - full path of the directory on the remote server where the files are saved to

## Dependencies

Make sure `watchdog` is installed.
```bash
pip install watchdog==0.10.2 argh==0.26.2
```

## Script Install

Installing it for Mac OS (>= Catalina)

```bash
mkdir -p $HOME/.rsynchanged/bin
echo "export PATH=\$PATH:$HOME/.rsynchanged/bin" >> ~/.zprofile
curl https://raw.githubusercontent.com/robertlucian/rsync-when-changed/master/remote_sync -o $HOME/.rsynchanged/bin/remote_sync
chmod +x $HOME/.rsynchanged/bin/remote_sync
```

And then source the profile

```bash
source ~/.zprofile
```

## Configuration

`INSTANCE_KEY` and `INSTANCE_ADDRESS` must both be set.
* `INSTANCE_KEY` - contains the path to the private key used for logging into the instance. 
* `INSTANCE_ADDRESS` - user and public DNS name of the instance. Has `[user@]public_dns_name` format.

Both of these variables should be exported in `~/.zprofile`.
