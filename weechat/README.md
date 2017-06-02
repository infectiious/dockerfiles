# Weechat relay dockerfile
## Docker container for running a [Weechat](https://github.com/weechat/weechat) relay for use with tools such as [Glowing Bear](https://github.com/glowing-bear/glowing-bear).

Make sure you have your both weechat server configuration and enabled relay in your configuration file. 

## Server configuration

Ensure your server configuration is set under irc.conf. 

Example irc.conf.
```
a.addresses = "ircserver.com/+5000"
a.proxy
a.ipv6
a.ssl = on
a.ssl_cert
a.ssl_priorities
a.ssl_dhkey_size
a.ssl_fingerprint
a.ssl_verify = off
a.password = "Username:Password"
```

## Enabling relay

Enable relay in the Weechat client
```
/setrelay.network.password yourpassword
/relay add weechat 9001
```

## Installation

```docker run -t -d -p 9001:9001 -v "(localweechatdirectory)":/weechat/.weechat infectiious/weechat-relay```


Image built on [Alpine](https://alpinelinux.org/).
