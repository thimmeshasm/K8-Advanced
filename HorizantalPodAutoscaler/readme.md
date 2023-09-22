# To add load on the php-apache application
1. Create a sample pod using ubuntu base image and exec into the p
reference   https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/

bewlow command create the load generator pod
kubectl run -i --tty load-generator --rm --image=busybox:1.28 --restart=Never

while sleep 0.01; do wget -q -O- http://php-apache; done
ok ok ok ok ok   increase load
kubectl get hpa --> check the load incresing
kubectl get pods
