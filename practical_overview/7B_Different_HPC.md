---
layout: page
title: 7B - Differences Between HPCs
---

Submitting Jobs to the Wolfpack 
================================

> Overview
> --------
> 
> **Objectives**
> 
> Understand the difference between between:
>    
>  * Available commands
> 
>  * Limits on time, storage space and other resources
>
> * Environment and site policies
>   
    



Different Scheduler Commands Across Different HPCs  
---------------------

When submitting a script, as we did in the previous session, there are slightly different commands **and** flags to customise the submission. 

An example includes requesting an interactive login session. In Wolfpack, the command is `qrsh`, NCI GADi is `qsub -I ` and UNSW Katana is `qsub -l`.

| Link | Details |
| ---- | ---- |
| [Garvan Wolfpack](https://gridscheduler.sourceforge.net/htmlman/htmlman1/qsub.html) | For Wolfpack HPC that is locally hosted at Garvan |
| [NCI GADI Submission](../img/job_submission.pdf) [NCI GADI Flags](../img/PBS_directives.pdf) | For Gadi HPC at NCI in Canberra |
| [UNSW Katana](https://docs.restech.unsw.edu.au/using_katana/running_jobs/) | For Katana HPC at UNSW |

Workflows for Beginners
----------------------------
Simon Yun has collated an expansive list of workflows, all of which are everyday ways to interact with your HPC of interest.  

1) Find out the queues and their status
   
2) Find out the site limits
   
3) Working interactively
   
4) Requesting more RAM
   
5) Requesting more RAM and **more** time
   
6) Requesting more RAM and more time and *more CPU cores**
   
7) Using a project code

## 1: find out the queues and their status

[workflow_1](../assets/img/flow_1.png)

| Category | Link | Details |
| ---- | ---- | ---- |
| Site queues | [Garvan](../assets/img/garvan_site_queues.pdf) | For Wolfpack HPC that is locally hosted at Garvan, login and then run:</br></br> `qstat -f`</br></br>|
| | [NCI](https://opus.nci.org.au/pages/viewpage.action?pageId=236881198) | For Gadi HPC at NCI in Canberra, login and then run:</br></br> `qstat -Q`</br></br> |
| | [UNSW](https://docs.restech.unsw.edu.au/using_katana/running_jobs/#get-information-about-the-state-of-the-scheduler) | For Katana HPC at UNSW, login and then run:</br></br> `pstat`</br></br> |

## 2: find out the site limits
**Note:** Site limits vary depending on the queue you select!

| Category | Link | Details |
| ---- | ---- | ---- |
| Site limits | [Garvan](./garvan_site_limits.pdf) | For Wolfpack HPC that is locally hosted at Garvan |
| | [NCI](https://opus.nci.org.au/pages/viewpage.action?pageId=236881198) | For Gadi HPC at NCI in Canberra |
| | [UNSW](https://docs.restech.unsw.edu.au/using_katana/running_jobs/#job-queue-limits-summary) | For Katana HPC at UNSW |

**Exceptions to site limits**

It's a good idea to **contact the support team at the specific site** if you have a **well justified** reason to apply for an exception to any of the published site limits:

| Category | Site | Details |
| ---- | ---- | ---- |
| Request an exception to site limits | Garvan | dsphelp@garvan.org.au |
| | NCI| help@nci.org.au |
| | UNSW | restech.support@unsw.edu.au |


## 3: begin working interactively
**Important Note:** You must request an `interactive job` whenever you work interactively.  

**Unless you request an interactive job (or submit a job to a queue), you should avoid heavy computation and data transfer activities!**

[workflow_1](../assets/img/flow_2.png)


| Category | Link | Details |
| ---- | ---- | ---- |
| Requesting an interactive session | [Garvan](./garvan_request_interactive.pdf) | For Wolfpack HPC locally hosted at Garvan |
| | [NCI](./nci_gadi_request_interactive.pdf) | For Gadi HPC at NCI in Canberra |
| | [UNSW](https://docs.restech.unsw.edu.au/using_katana/running_jobs/#interactive-jobs) | For Katana HPC at UNSW |

## 4: requesting more RAM
To request 16GB RAM, modify Section 3 with:

| Category | Site | Details |
| ---- | ---- | ---- |
| Request more RAM | Garvan | `qlogin -l mem_requested=16G` |
| | NCI| `qsub -I -l mem=16gb` |
| | UNSW | `qsub -I -l select=1:mem=16gb` |

## 5: requesting more RAM + more time
To request 1 hour 30 minutes of time:

| Category | Site | Details |
| ---- | ---- | ---- |
| Request more RAM + more time | Garvan | `qlogin -l mem_requested=16G,h_rt=01:30:00` |
| | NCI| `qsub -I -l mem=16gb,walltime=01:30:00` |
| | UNSW | `qsub -I -l select=1:mem=16gb,walltime=01:30:00` |

## 6: requesting more RAM + more time + more cpu-cores
To request 4 cpu-cores:


| Category | Site | Details |
| ---- | ---- | ---- |
| Request more RAM + more time + more cpu-cores | Garvan | `qlogin -l mem_requested=16G,h_rt=01:30:00 -pe smp 4`</br></br>**Important note:**</br></br> $total\space memory = mem\_requested \times cpucores$ |
| | NCI| `qsub -I -l mem=16gb,ncpus=4,walltime=01:30:00` |
| | UNSW | `qsub -I -l select=1:mem=16gb,ncpus=4,walltime=01:30:00` |


## 7: using a project code
Replace `<my_Garvan_project>`, `<my_UNSW_project>` and `<my_NCI_project>` as appropriate for your own case.


| Category | Site | Details |
| ---- | ---- | ---- |
| Use a project code | Garvan | `qlogin -P <my_Garvan_project> -l mem_requested=16G,h_rt=01:30:00 -pe smp 4`</br></br>**Useful note:**</br></br> Use: `qconf -sprjl` to see the list of projects. |
| | NCI|  `qsub -I -P <my_NCI_project> -l mem=16gb,ncpus=4,walltime=01:30:00`</br></br>**Note:**</br></br>Use: `nci_account` to see your NCI project code. |
| | UNSW |  `qsub -I -P <my_UNSW_project> -l select=1:mem=16gb,ncpus=4,walltime=01:30:00` |




-----

Adapted from the Data Carpentry Intro to Command Line -shell genomics https://datacarpentry.org/shell-genomics/

Licensed under CC-BY 4.0 2018–2021 by The Carpentries  
Licensed under CC-BY 4.0 2016–2018 by [Data Carpentry](http://datacarpentry.org)
