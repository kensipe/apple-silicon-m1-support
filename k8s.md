# Kubernetes Support on M1

Spinning up [Minikube](https://minikube.sigs.k8s.io/docs/start/) or [KinD](https://kind.sigs.k8s.io/) works fine.  I have a Certified Kubernetes Application Developer ([CKAD](https://github.com/kensipe/ckad-labs)) course which had no issues.  However when I started testing out my istio or [day2-networking](https://github.com/kensipe/d2-networking) course I ran into issues with `istiod`.   This is true for minikube or kind.  It appears that the probes fail resulting in the service not being ready, then eventually that pod is killed and restarted to repeat the process.

This could be an issue on my side.  I believe this is the first time I've used docker as the underlying hypervisor for minikube (I usually have virtualbox) and I've never tried to run istio on KinD before.

From the event logs

```sh
13s         Warning   Unhealthy           pod/istiod-64dbd46f7-75khs                   Readiness probe failed: Get "http://10.244.0.5:8080/ready": dial tcp 10.244.0.5:8080: connect: connection refused

11s         Warning   BackOff             pod/istiod-64dbd46f7-75khs                   Back-off restarting failed container
```

## notes

* This is deployment of iostio 1.8 with known working manifests (from labs)
* This is deployed to known working versions of kubernetes
* The differences that exist are:
    * New M1 Architecture (could be an istio image support issue)
    * Hypervisor
* May need to upgrade istio

Next step is to get an exact configuration match with older laptop and work from there.  I'm unable to find others having this issue on the inter-webs.

## Updates

* Ran into this from Apr 2021: [Istio does not currently support ARM](https://github.com/istio/istio/issues/30829) which includes a fix the istiod: https://github.com/istio/istio/issues/30829#issuecomment-903158774
But does not fix the side cars

Time to make the donuts!

