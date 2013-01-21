lightsocks
===========

We walk in the dark, to serve the light.

shadowsocks is a lightweight tunnel proxy which can help you get through firewalls

This is a special client serving as a transparent proxy. Once set up, you can
visit `localhost:local_port` as if you are visiting `target_server:target_port`.

usage
-----------

First, set up [shadowsocks](https://github.com/clowwindy/shadowsocks) server
on your VPS.

Then edit `config.json`, change the following values:

    server          your server ip or hostname
    server_port     server port
    local_port      local port
    password        a password used to encrypt transfer
    target_server   the server you want to visit, for example, github.com
    target_port     the server port you want to visit, for example, 22

Run `python lightsocks.py` on your client machine.

visit `localhost:local_port` as if you are visiting `target_server:target_port`.

FAQ
-----------

Q: How to setup git with Github?

A: Edit ~/.ssh/config, add the following:

    host github.com
    port 1082
    hostname 127.0.0.1

Replace `1082` with your `local_port` if your `local_port` is not 1082. Then
you're done.
