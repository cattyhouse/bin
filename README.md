# useful binary
- release syntax 
  - `tag=${name}-${version}`
  - `binary=${name}-${version}-$(uname -m)`
  - `url=https://github.com/cattyhouse/bin/releases/download/${tag}/${binary}`
- caddy for example :
  - name: `caddy`
  - version : `v2.6.4`
  - $(uname -m) output : `x86_64`
  - url : `https://github.com/cattyhouse/bin/releases/download/caddy-v2.6.4/caddy-v2.6.4-x86_64`
    - download and install
      - `curl -sfL -o /usr/local/bin/caddy https://github.com/cattyhouse/bin/releases/download/caddy-v2.6.4/caddy-v2.6.4-x86_64`
      - `chmod +x /usr/local/bin/caddy`

- usage in shell script

```sh
#!/bin/sh
arch=$(uname -m)
caddy_ver="v2.6.4"
caddy_url="https://github.com/cattyhouse/bin/releases/download/caddy-${caddy_ver}/caddy-${caddy_ver}-${arch}"

curl -sfL -o /usr/local/bin/caddy "$caddy_url" ||
{ echo "failed to download caddy-${caddy_ver}-${arch}" ; exit 1 ; }

chmod +x /usr/local/bin/caddy
```
