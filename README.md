## Use Pi-hole on container

Inside of this folders you can find deploy files to run Pi-hole in each container solution.


## Note

If you are using kubernetes you need to remove `traefik` service LoadBalancer, because it uses the same ports of Pi-hole 443 and 80.

To do that, you just need to execute
```bash
  kubectl delete -n kube-system helmcharts traefik
```

After that you are able to create deployment and service.

## Note

If you are having problems when using domain name to access pi-hole or when it's used behind a reverse proxy, then you should
try to copy the file `external.conf` to this path on pi-hole folders:

```bash
  /etc/lighttpd/conf-enabled/
```
or you can also edit directely the file `/etc/lighttpd/lighttpd.conf` adding this line at the end:

```bash
  setenv.add-environment = ( "VIRTUAL_HOST" => "your.domain" )
```
After this you need to restart lighttpd using this command:

```bash
  sudo service lighttpd restart
```

Enjoy it!


## Autores

- [@TnioA](https://github.com/TnioA)

