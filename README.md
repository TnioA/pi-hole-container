## Use Pi-hole on container

Inside of this folders you can find deploy files to run Pi-hole in each container solution.


## Note

If you are using kubernetes you need to remove `traefik` service LoadBalancer, because it uses the same ports of Pi-hole 443 and 80.

To do that, you just need to execute
```bash
  kubectl delete -n kube-system helmcharts traefik
```

After that you are able to create deployment and service.

Enjoy it!


## Autores

- [@TnioA](https://github.com/TnioA)

