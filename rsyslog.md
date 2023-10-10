# my first linux documentation

Today, I learned about rsyslog in ubuntu server

## Commands I Used

- `apt install rsyslog`: To begin, you should install rsyslog on your Ubuntu server if it is not already installed. You can do this with this command
- `systemctl status rsyslog.service`: Additionally, you can check the status of rsyslog on your Ubuntu server using systemctl
## Configuring Your Server as a Log Server

If you want to configure your server as a log server in your company, here's a hint you need to know: In the `/etc/rsyslog.conf` file, there is a section that you have to uncomment, and it is as follows:

```
# Provides UDP syslog reception
# module(load="imudp")
# input(type="imudp" port="514")

# Provides TCP syslog reception
# module(load="imtcp")
# input(type="imtcp" port="514")
```
## Configuring Your Server to send logs into log server
if you want to configure your server to send logs into log server, here is a hint you need to know: in the `/etc/rsyslog.conf` file, you have to write this commands to done this task

- send as udp: `*.* @<remote-server>:514`
- send as tcp: `*.* @@<remote-server>:514`

