# P4NIS
This is the branch for the P4NIS wireless network. Currently, it includes some source codes and experimental results.

# Architecture
![image](https://github.com/KB00100100/P4NIS/blob/master/P4NIS_architecture.png)

# run P4NIS 
## client
```
p4c --target bmv2 --arch V1model p4nis_s2.p4 //make 
simple_switch --log-console -i 0@enp2s0 -i 1@veth0 -i 2@veth2 -i 3@veth4 p4nis_s1.json  // run a bmv2 switch
// open a new terminal
./runtime_CLI.py < s2-runtime.txt //install the runtime table
```
## server
```
p4c --target bmv2 --arch V1model p4nis_s2.p4 // make
simple_switch --log-console -i 0@veth0 -i 1@enp8s0f2 -i 2@enp8s0f1 -i 3@enp8s0f0 p4nis_s2.json // run a bmv2 switch
// open a new terminal
./runtime_CLI.py < s2-runtime.txt //install the runtime table
```
