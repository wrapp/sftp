
Easy to use SFTP ([SSH File Transfer Protocol](https://en.wikipedia.org/wiki/SSH_File_Transfer_Protocol)) server with [OpenSSH](https://en.wikipedia.org/wiki/OpenSSH).

Usage
-----

- Define users arguments in `SFTP_USER`, `SFTP_PASSWORD` and `SFTP_UID` environment variables to `docker run`

Examples
--------


```
docker run -e SFTP_USER=foo -e SFTP_PASSWORD=bar  -p 2222:22 -d docker.wrops.net/sftp:master
```
