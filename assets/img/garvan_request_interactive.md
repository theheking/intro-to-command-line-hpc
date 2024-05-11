![](https://images.contentstack.io/v3/assets/blt324fd0a04af716e6/blt3f0048229394c515/6405de96205f2b7a60b745d6/gimr-logo.png)
# Garvan: Request interactive session
This document is a simple walk-through that shows how an interactive session is requested and used on Garvan's on-site HPC platforms.

**Source documents:**

TBD

## Wolfpack
### Login on the login node
```shell

# Login to Wolfpack HPC

ssh -i <your-SSH-key> <your-username>@dice01.garvan.unsw.edu.au

```

### Request an interactive session from the scheduler

```shell

# Request an interactive session

qlogin

```
### Wait for interactive session to start
On Wolfpack, interactive sessions will start almost instantly!

### Interactive session starts

![Garvan: request interactive session](garvan_qlogin_2.png)

### Start R/Python/Julia/Perl...etc.

![Garvan: start interactive task](garvan_start_interact_2.png)

### Exit interactive session and logout

![Garvan: exit](garvan_end_interactive_2.png)