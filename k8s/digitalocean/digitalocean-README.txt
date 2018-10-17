========================================
======Digital Ocean=====================
========================================

- Apply DigitalOcean secret 

Currently Digitalocean does not support loadbalancer as default
So , I have to apply this scripts 

https://github.com/digitalocean/digitalocean-cloud-controller-manager


- Apply DigitalOcean cloud controller


- Setup DigitalOcean LoadBancer
        Forwading rules 
            TCP on port 80  TCP on port 32489
            TCP on port 443  TCP on port 30414
        Health checks
            tcp://0.0.0.0:30410

            Check Intervals 20
            Response Timeout 10
            Unhealty Threshold 3
            Healty Threshold 5


- Container Storage setup

kubectl apply -f https://raw.githubusercontent.com/digitalocean/csi-digitalocean/master/deploy/kubernetes/releases/csi-digitalocean-v0.2.0.yaml