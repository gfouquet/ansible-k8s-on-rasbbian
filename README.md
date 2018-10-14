Deploy Kubernetes on a Raspberry PI cluster
===========================================

Designed / tested on a Mac

Based on [K8s on Raspbian] and [K8s on Hypriot]

I made this for the sake of learning, there probably have better proof tested solutions such as [rak8s] 
(which I did not try)

Prerequisites :
* ansible 2.5+
* 2 or more Raspberry PIs
* raspbian distribution 


Install cluster
---------------

This performs a basic install of Kubernetes on a cluster od Raspberry PI.
It's *not* a production-grade install

1. Burn sd card with raspbian
2. While sd card mounted, run `setup-boot.sh` 
3. Switch on PIs
4. Get their IPs from router admin
5. Input IPs in `host_vars` files
6. run `ansible-playbook -i hosts install-cluster.yml` 


Install dashboard
-----------------
When cluster is installed, you can install kubernetes dashboard 
by running `ansible-playbook -i hosts install-dashboard.yml`


Cleanup
-------

The `cleanup.yml` playbook resets kubernetes which is required before reinstalling it. 
This playbook is experimental 


Local machine (Writing in Progress) 
-----------------------------------
* install kubectl and cluster config file
* install the correct version of helm (should match installed tiller) - tricky with homebrew
* access dashboard : `kubectl proxy& ` then [http://localhost:8001/api/v1/namespaces/kube-system/services/kubernetes-dashboard/proxy/#!/about?namespace=default]


[K8s on Raspbian]: https://gist.github.com/alexellis/fdbc90de7691a1b9edb545c17da2d975
[K8s on Hypriot]: https://blog.hypriot.com/post/setup-kubernetes-raspberry-pi-cluster/
[rak8s]: https://rak8s.io/
