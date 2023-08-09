**devops_assignment1_part3**


**Step 1**

Using my image: https://hub.docker.com/repository/docker/abdul7235/greeting-app/general

**Step 2**

**Command:** docker run -p 8000:8000 --name greeting-container greeting-app

**Output:** INFO:     Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)
INFO:     Started parent process [7]
INFO:     Started server process [10]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Started server process [9]
INFO:     Waiting for application startup.
INFO:     Application startup complete.


**Step 3**

**Command:** docker ps

**Output:** CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                    NAMES
        232ba96ce6c6   greeting-app   "/bin/sh -c 'uvicorn…"   3 minutes ago   Up 3 minutes   0.0.0.0:8000->8000/tcp   greeting-container


**Command:** docker stop greeting-container

**Output:** greeting-container

**Command:** docker rm greeting-container

**Output:** greeting-container


**Command:** docker logs greeting-container

**Output:** INFO:     Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)
INFO:     Started parent process [7]
INFO:     Started server process [9]
INFO:     Started server process [10]
INFO:     Waiting for application startup.
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Application startup complete.
INFO:     172.17.0.1:37134 - "GET /docs HTTP/1.1" 200 OK
INFO:     172.17.0.1:37134 - "GET /openapi.json HTTP/1.1" 200 OK
INFO:     172.17.0.1:47692 - "GET /api/greeting/?name=Abdul&specie=Human HTTP/1.1" 200 OK
INFO:     172.17.0.1:42946 - "GET /api/greeting/?name=Mayo&specie=Cat HTTP/1.1" 200 OK
INFO:     172.17.0.1:42956 - "GET /api/greeting/?name=Bruno&specie=Dog HTTP/1.1" 200 OK


**Command:** docker inspect greeting-container

**Output:** [
    {
        "Id": "3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058",
        "Created": "2023-08-08T17:34:57.639596747Z",
        "Path": "/bin/sh",
        "Args": [
            "-c",
            "uvicorn app:app --host 0.0.0.0 --port 8000 --workers 2"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 1879,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2023-08-08T17:34:58.285468959Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:7fa46e551755f98018092650e9c6c061cffb3846ddf1949813e9480415729aff",
        "ResolvConfPath": "/var/lib/docker/containers/3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058/hostname",
        "HostsPath": "/var/lib/docker/containers/3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058/hosts",
        "LogPath": "/var/lib/docker/containers/3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058/3c950b6cb25f5d38498d7cf89a53270bec6014ed024732d1a911e5b218cbe058-json.log",
        "Name": "/greeting-container",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {
                "8000/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "8000"
                    }
                ]
            },
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                30,
                120
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/6e3ff218bd52d279e1ebf2820605542c78fef14e7d0a553f86d30cc3b9c72c93-init/diff:/var/lib/docker/overlay2/zm0r8qz5qwv8sfo33vd8cl342/diff:/var/lib/docker/overlay2/rfj3xsbstu034z6qsqvhm0z2b/diff:/var/lib/docker/overlay2/evpfj9kijek7mnyw9hgblke22/diff:/var/lib/docker/overlay2/977e651a81cd4753a35f7947e9e7a3781cc7a163bcfd2bb63c5a55fea90fd480/diff:/var/lib/docker/overlay2/34495ae640a47eb105523cc74d0a210fa1b803f833e0bed52cd4e486fcf90223/diff:/var/lib/docker/overlay2/9ebf6a97c6841b076e2997360f02f13c137d6da467beb01c5247483abd2d2d2b/diff:/var/lib/docker/overlay2/ab0dfa21ee9611755f5d5ac90e73fa64062031eca2da3a1f87e8258fc104a763/diff:/var/lib/docker/overlay2/21b1bfdb5d3a957ee49695611492c1ab3520cccf2859a8922280acc09acc5a2b/diff:/var/lib/docker/overlay2/44dfde025d97768f2f09e75fe7f180b1655d94a8b7eb4531216ddb5a34759ece/diff:/var/lib/docker/overlay2/c7f233882e73420e45e6aa4b0bb221d7a80cfd60b43473edbd7f53bc93a3e034/diff:/var/lib/docker/overlay2/65c4e431349c6ba9b970efef0d5c8e50458cd276481850e7f86bf054e14b7457/diff",
                "MergedDir": "/var/lib/docker/overlay2/6e3ff218bd52d279e1ebf2820605542c78fef14e7d0a553f86d30cc3b9c72c93/merged",
                "UpperDir": "/var/lib/docker/overlay2/6e3ff218bd52d279e1ebf2820605542c78fef14e7d0a553f86d30cc3b9c72c93/diff",
                "WorkDir": "/var/lib/docker/overlay2/6e3ff218bd52d279e1ebf2820605542c78fef14e7d0a553f86d30cc3b9c72c93/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "3c950b6cb25f",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": true,
            "AttachStderr": true,
            "ExposedPorts": {
                "8000/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "LANG=C.UTF-8",
                "GPG_KEY=A035C8C19219BA821ECEA86B64E628F8D684696D",
                "PYTHON_VERSION=3.11.4",
                "PYTHON_PIP_VERSION=23.1.2",
                "PYTHON_SETUPTOOLS_VERSION=65.5.1",
                "PYTHON_GET_PIP_URL=https://github.com/pypa/get-pip/raw/0d8570dc44796f4369b652222cf176b3db6ac70e/public/get-pip.py",
                "PYTHON_GET_PIP_SHA256=96461deced5c2a487ddc65207ec5a9cffeca0d34e7af7ea1afc470ff0d746207"
            ],
            "Cmd": null,
            "Image": "greeting-app",
            "Volumes": null,
            "WorkingDir": "/devops_assignment1_part1",
            "Entrypoint": [
                "/bin/sh",
                "-c",
                "uvicorn app:app --host 0.0.0.0 --port 8000 --workers 2"
            ],
            "OnBuild": null,
            "Labels": {}
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "612c96731e9c02306675f02e1ed54c20e6ca0b8f590e51cf2332abc4fa05200e",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "8000/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "8000"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/612c96731e9c",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "c463470a4d9af1a363a53aac726c7c22b92b0ce8b4f7e9f2ed4f781f27b4c572",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "dc1b590c29b672a902935dbc6e9a0daa659541905940fef8fe25ef948c32f88d",
                    "EndpointID": "c463470a4d9af1a363a53aac726c7c22b92b0ce8b4f7e9f2ed4f781f27b4c572",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]



**Command:** docker exec greeting-container ls

**Output:** Dockerfile
README.md
app.py
models
requirements.txt

**Command:** docker run -it -p 8000:8000 --name greeting-container greeting-app

**Command:** docker start -it greeting-container

**Command:** docker attach greeting-container

**Output:** On pressing Ctrl + C
INFO:     Shutting down
INFO:     Shutting down
INFO:     Waiting for application shutdown.
INFO:     Application shutdown complete.
INFO:     Finished server process [10]
INFO:     Waiting for application shutdown.
INFO:     Application shutdown complete.
INFO:     Finished server process [9]
INFO:     Stopping parent process [7]


**Command:** docker commit greeting-container container-app2.0

**Output:** sha256:9ca7e4638140504213072ce0655c98cd1b3196a43d381723aa69b436a75c6c15


**Command:** docker stats greeting-container

**Output:**

CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.47%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.47%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.47%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.47%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.50%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.50%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME                 CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-container   0.60%     111.4MiB / 7.679GiB   1.42%     1.16kB / 0B   0B / 0B     5

**Command:** docker top greeting-container

**Output:**

UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                2225                2204                0                   18:03               ?                   00:00:00            /bin/sh -c uvicorn app:app --host 0.0.0.0 --port 8000 --workers 2
root                2262                2225                0                   18:03               ?                   00:00:00            /usr/local/bin/python /usr/local/bin/uvicorn app:app --host 0.0.0.0 --port 8000 --workers 2
root                2263                2262                0                   18:03               ?                   00:00:00            /usr/local/bin/python -c from multiprocessing.resource_tracker import main;main(4)
root                2264                2262                0                   18:03               ?                   00:00:02            /usr/local/bin/python -c from multiprocessing.spawn import spawn_main; spawn_main(tracker_fd=5, pipe_handle=7) --multiprocessing-fork
root                2265                2262                0                   18:03               ?                   00:00:02            /usr/local/bin/python -c from multiprocessing.spawn import spawn_main; spawn_main(tracker_fd=5, pipe_handle=9) --multiprocessing-fork


**Command:** docker start greeting-container

**Output:** greeting-container

**Command:** docker pause greeting-container

**Output:** 

CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS                   PORTS
  NAMES
8eb79a2a18ba   greeting-app   "/bin/sh -c 'uvicorn…"   22 minutes ago   Up 13 minutes (Paused)   0.0.0.0:8000->8000/tcp   greeting-container

**Command:** docker unpause greeting-container

**Output:** 

CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                    NAMES
8eb79a2a18ba   greeting-app   "/bin/sh -c 'uvicorn…"   23 minutes ago   Up 13 minutes   0.0.0.0:8000->8000/tcp   greeting-container


**Command:** docker rename greeting-container greeting-appc

**Output:** 

CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                    NAMES
8eb79a2a18ba   greeting-app   "/bin/sh -c 'uvicorn…"   38 minutes ago   Up 28 minutes   0.0.0.0:8000->8000/tcp   greeting-appc

**Command:** docker wait greeting-appc

**Output:** 137

**Command:** docker port greeting-appc

**Output:** 1378000/tcp -> 0.0.0.0:8000


**Command:** docker update docker update --cpus 2 --memory 512m --memory-swap 512m greeting-appc

**Output:** The stats percentages have changed after updating container resources

CONTAINER ID   NAME            CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-appc   0.56%     111.5MiB / 512MiB   21.77%    1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME            CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-appc   0.55%     111.5MiB / 512MiB   21.77%    1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME            CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-appc   0.55%     111.5MiB / 512MiB   21.77%    1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME            CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-appc   0.36%     111.5MiB / 512MiB   21.77%    1.16kB / 0B   0B / 0B     5
CONTAINER ID   NAME            CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
8eb79a2a18ba   greeting-appc   0.36%     111.5MiB / 512MiB   21.77%    1.16kB / 0B   0B / 0B     5


**Command:** docker restart greeting-appc

**Output:** 

CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                    NAMES
8eb79a2a18ba   greeting-app   "/bin/sh -c 'uvicorn…"   49 minutes ago   Up 19 seconds   0.0.0.0:8000->8000/tcp   greeting-appc

