# SSH

A SSH "jump host" is deployed with this chart to allow users to use `scp` and `sftp` to copy files to the NFS. Each notebook server starts its own SSH service, allowing users to access their notebook servers using `ssh` via the jump host.

If a user wants to utilize this, they should perform the following steps:
1. Launch their notebook server.
2. Start a terminal and open the file `~/.ssh/authorized_keys` with a text editor.
3. On their local machine, generate a new or reuse an old SSH public key. Add their public key as a new line in the file from (2).
4. Edit the file `~/.ssh/config` on their local machine to include the following:
```
Host lsst-hub-ssh
    User <username>
    Hostname ssh.lsst.dirac.dev

Host lsst-hub
    User <username>
    Hostname lincc-<username>.notebooks
    ProxyJump lsst-hub-ssh
```
For example:
```
Host lsst-hub-ssh
    User stevenstetzler
    Hostname ssh.lsst.dirac.dev

Host lsst-hub
    User stevenstetzler
    Hostname lincc-stevenstetzler.notebooks
    ProxyJump lsst-hub-ssh
```

5. On your local machine, ssh to your running notebook server: `ssh lsst-hub`. Alternatively, run the full command: `ssh -J <username>@ssh.lsst.dirac.dev <username>@lincc-<username>.notebooks`
