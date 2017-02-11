## BOSH Web Proxy Release

Enables iweb proxy configuration

## Usage

Include the release:

```yaml
releases:
  name: webproxy_release
  version: latest
```

In this example, we use BOSH's [Runtime Config](https://bosh.io/docs/runtime-config.html) to customize `http_proxy`, `https_proxy` and `no_proxy` environment variables.

```yaml
addons:
- name: webproxy
  jobs: 
  - name: webproxy
    release: webproxy_release
    properties:
      env:
        http_proxy: http://theproxy.com
        https_proxy: https://theproxy.com
        no_proxy: 10.0.0.0
```

