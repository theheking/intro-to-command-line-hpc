![](https://images.contentstack.io/v3/assets/blt324fd0a04af716e6/blt3f0048229394c515/6405de96205f2b7a60b745d6/gimr-logo.png)
# NCI Gadi: Site queues
```shell

# Login to the NCI Gadi HPC

ssh -i <your-SSH-key> <your-username>@gadi.nci.org.au
```
```shell

# Show all the queue names

qstat -q

# Show details of queues that are commonly used

qstat -q | grep -v TBD | uniq

```

```shell

# Show more details of a specific queue 

qstat -q TBD
```
```shell

# Show the capabilities of all the compute nodes in the system

pbsnodes -a
```
```shell

# Logout 

exit
```