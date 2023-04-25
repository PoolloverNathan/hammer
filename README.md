# hammer
When a [crowbar](//github.com/q3k/crowbar) just isn't enough...

Hammer is a browser extension/client/server setup that allows forwarding arbritrary (but I strongly recommend ssh/vpn) connections through *really* evil proxies via your existing browser tunnel.

| Problem | Symptom | Workaround |
| :------ | :------ | :--------- |
| Your proxy uses NTLM. | All authentication attempts will fail. | An HTTP upgrade is used to allow Chrome to do the authentication. |
| Your proxy injects MITM certificates. | Every request made from outside Chrome gives an SSL error. | The Chrome extension uses Chrome's trusted certificates. |
| Your proxy assumes `CONNECT` always means HTTP. | Trying to forward SSH over your proxy causes it to complain about bad HTTP syntax. | The Chrome extension uses an HTTP upgrade, which starts off looking enough like HTTP. |
