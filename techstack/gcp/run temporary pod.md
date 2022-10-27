#gcp #cloud 

How to run a [[pod]] with an interactive session attached:

```sh
kubectl run test-1 --labels app=foo --image=alpine --restart=Never --rm --stdin --tty
```

**Note:** The kubectl switches used here in conjunction with the run command are important to note.

`--stdin` ( alternatively `-i` ) creates an interactive session attached to STDIN on the container.

`--tty` ( alternatively `-t` ) allocates a TTY for each container in the pod.

`--rm` instructs Kubernetes to treat this as a temporary Pod that will be removed as soon as it completes its startup task. As this is an interactive session it will be removed as soon as the user exits the session.

`--label` ( alternatively `-l` ) adds a set of labels to the pod.

`--restart` defines the restart policy for the Pod