![](https://images.contentstack.io/v3/assets/blt324fd0a04af716e6/blt3f0048229394c515/6405de96205f2b7a60b745d6/gimr-logo.png)
# NCI Gadi: Request interactive session

### Login on the login node
```shell

# Login to Gadi HPC

ssh -i <your-SSH-key> <your-username>@gadi.nci.org.au

```

### Request an interactive session from the scheduler

```shell

# Request an interactive session

qsub -I

```
### Wait for interactive session to start
On Gadi, interactive sessions can take a few minutes to start!
![NCI Gadi - wait in queue for an interactive session](./nci_gadi_start_interact_1.png)
### Interactive session starts

### Start R/Python/Julia/Perl...etc.
![NCI Gadi - begin task](./nci_gadi_start_interact_4.png)
### Exit interactive session and logout
![NCI Gadi - end session and logout](./nci_gadi_end_interact.png)