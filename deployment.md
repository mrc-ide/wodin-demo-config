# Deployment notes for RESIDE

Not for use by users.

This will improve once we get a real deployment system up and running.

* Check that the host part of `baseUrl` is correct and the protocol is https
* Check that the `savePrefix` and path component of `baseUrl` are unique within the deployment
* Edit the `deploy` script to add a new container that loads this configuration. Typically we use `wodin-<name>` for a deployment with basename of `<name>`
* Edit the `proxy/nginx.conf` settings to proxy `<name>` to this new container. You will need to do both a 301 redirect for the slash-less version and a `proxy_pass` for the version with a slash
