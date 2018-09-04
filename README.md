Deploy Kubernetes on a Raspberry PI cluster
===========================================

Designed / tested on a Mac
Based on [K8s on Raspbian]

Prerequisites :
* ansible

1. Burn sd card
2. While sd card mounted, run `setup-boot.sh` 
3. Switch on PIs
4. Get their IPs from router admin
5. Input IPs in `host_vars` files
6. run `ansible-playbook -i hosts site.yml` 

[K8s on Raspbian]: https://gist.github.com/alexellis/fdbc90de7691a1b9edb545c17da2d975
