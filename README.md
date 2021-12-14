# Mini Container
I developed a Docker similar tool (in Python), which can start a container instance with configuration parameters (e.g., namespace and cgroups). I used four namespaces, which are UTS, network, mount, and PID, and two control groups, which are cpuset and memory. I called it miniDocker.

Here is a provided a root file system that you can download from:
http://www.cs.binghamton.edu/~huilu/slidesfall2021/ubuntu-rootfs.tar.gz.
Place “ubuntu-rootfs.tar.gz” under your working directory (where you run your miniDocker) and unzip
it:

```
$mkdir new_root
$tar xvf ubuntu-rootfs.tar.gz -C new_root/
```

Dowload the following two program binaries and place them under ./new_root/home/
```
http://www.cs.binghamton.edu/~huilu/slidesfall2021/loop
http://www.cs.binghamton.edu/~huilu/slidesfall2021/mem
```
Now, the new root filesystem is ready. You can use it as the root file system of the container instance. You can execute the following code now.

```
python3  miniDocker.py --hostname tester --ip_addr 10.0.0.20 --mem_size 10 --cpu 2 --root_path ./new_root
```


## Role Variables

| Variable        | Required | Default       | Choices                   | Comments                               |
| --------------- | -------- | ------------- | ------------------------- | -------------------------------------- |
| hostname        | yes      | administrator |                           | Hostname of the container.             |
| ip_addr         | yes      | 10.0.0.1      |                           | Ip Address of the container.           |
| mem_size        | yes      | 10            | --mem                     | Memory size in MB for container.       |
| cpu_num         | yes      | 1             |                           | CPU number for the container.          |
| root_path       | yes      | ./new_root    | --cpu                     | Path of the root file directory.       |

## Requirements
- Python3
- Python3 unshare package
- Python3 argparse package
- Python3 os package
- Python3 sys package

## Supported Distributions
- Centos7
- Debian10
- Debian11
- Pardus18
- Debian9
- Fedora30
- Pardus19.0
- Ubuntu16.04
- Ubuntu18.04
- Ubuntu19.04
- Ubuntu19.10
- Ubuntu20.04

## Author Information
Yigithan Saglam - saglamyigithan@gmail.com
