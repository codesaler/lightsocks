lightsocks
===========

We walk in the dark, to serve the light.

[shadowsocks](https://github.com/clowwindy/shadowsocks) is a lightweight tunnel proxy which can help you get through firewalls

lightsocks is a shadowsocks client serving as a transparent proxy. Once set up, you can
visit `localhost:local_port` as if you are visiting `target_server:target_port`.

usage
-----------

First, set up [shadowsocks](https://github.com/clowwindy/shadowsocks) server
on your VPS.

Then edit `config.json`, change the following values:

    server          your shadowsocks server ip or hostname
    server_port     your shadowsocks server port
    password        your shadowsocks password
    local_port      local port
    target_server   the server you want to visit, for example, github.com
    target_port     the server port you want to visit, for example, 22

Run `python lightsocks.py` on your client machine.

visit `localhost:local_port` as if you are visiting `target_server:target_port`.

FAQ
-----------

Q: How to setup git ssh with Github?

A: Edit `config.json`, set `target_server` to `github.com`, set `target_port`
 to `22`. Run `python lightsocks.py`   
 
Edit ~/.ssh/config, add the following:

    host github.com
    port 1082
    hostname 127.0.0.1

Replace `1082` with your `local_port` if your `local_port` is not 1082. Then
you can `git clone git@github.com:myname/myrepo.git`

Q: What about git:// protocol?

A: Similar to the above. But you'll set both `target_port` and `local_port` 
to 9418. Then add '127.0.0.1 github.com' in your `/etc/hosts` file.
Then you can `git clone git://github.com/clowwindy/shadowsocks.git`
