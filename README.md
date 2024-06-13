tested on:
check-mk-raw:2.3.0
kubernetes v1.23.6

#Volume called tmpfs with emptyDir set to use memory (medium: Memory). This creates a temporary file system in RAM that the container can use for temporary storage, as specified by tmpfs in Docker. I noticed an improvement in performance. Like a https://docs.checkmk.com/latest/en/introduction_docker.html

#Volume called localtime with hostPath pointing to /etc/localtime. This mounts the node's time file to the container, ensuring that the container uses the same time zone setting as the Docker node, in read-only mode (readOnly: true). Like a https://docs.checkmk.com/latest/en/introduction_docker.html

#Ingress updated from networking.k8s.io/betav1 to networking.k8s.io/v1

#PVC dont use storageClass to solve "Bad file descriptor" - (#2) - when I used a storageclass, PV used the default storage settings (nfs v4). I changed the edeploy options to use (nfs V3).

#PV set Options to solve "Bad file descriptor" problem - (#2) - when I used a storageclass, PV used the default storage settings (nfs v4). I changed the edeploy options to use (nfs V3).

#Service expose 8000 TCP port to Agent Receiver
