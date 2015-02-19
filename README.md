sftp [![Docker Build Status](http://hubstatus.container42.com/atmoz/sftp)](https://registry.hub.docker.com/u/atmoz/sftp)
====

Easy to use SFTP ([SSH File Transfer Protocol](https://en.wikipedia.org/wiki/SSH_File_Transfer_Protocol)) server with [OpenSSH](https://en.wikipedia.org/wiki/OpenSSH).

Usage
-----

- Define users arguments in `SFTP_USER`, `SFTP_PASSWORD` and `SFTP_UID` environment variables to `docker run`
  - You must set custom UID for your users if you want them to make changes to
    your mounted volumes with permissions matching your host filesystem.
- Mount volumes in user's home folder.
  - The users are chrooted to their home directory, so you must mount the
    volumes in separate directories inside the user's home directory
    (/home/user/**mounted-directory**).

Examples
--------

### Single user and volume

```
docker run \
    -e SFTP_USER=foo -e SFTP_PASSWORD=bar -e SFTP_UID=1001 \
    -v /host/share:/home/foo/share \
    -p 2222:22 -d atmoz/sftp
```
