## LAB: Multipass-SSH-Configuration (Create Ansible Test Environment)

This scenario shows:
- how to install multipass
- how to create control node, managed nodes
- how to configure ssh between control node and managed nodes



### Steps
#### creating controlnode, managed nodes (node1, node2, etc.)
- Create three ec2 instance(ubuntu ami) on aws. controlnode node1 ,node2

- Connect Control vm by opening shells (make sure ssh port is open in aws security group of control node)

``` 
ssh -i "instance-pem-key-path" ubuntu@ip_address_of_controlnode
``` 

- install net tools
``` 
sudo apt update
sudo apt install net-tools
# to see IPs
ifconfig
``` 

- Create ssh public key on control plane
- Copy the public key from control plane to node1 and node2

``` 
> on controlnode
ssh-keygen (no password, enter 3 times)
cat ~/.ssh/id_rsa.pub (copy the value)
``` 

![image](https://user-images.githubusercontent.com/10358317/201083201-8e0a9bfb-8001-429e-881f-d38a7c970015.png)

- Paste copied public key (control plane) into the authorized_keys in each managed nodes.

``` 
cd .ssh (on each workers)
nano authorized_keys 
> Paste keys from controlnode (hence managed nodes know the controlnode IP and public key, controlnode can connect it)
``` 

- get IPs of all nodes

```
multipass list
```

- SSH from controlplane to node1

```
ssh <IP>
or 
ssh <username>@<IP>
```

### References
- https://techsparx.com/linux/multipass/enable-ssh.html
