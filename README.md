**devops_assignment1_part3**


**Step 1**

**Command:** docker volume create my_volume

**Command:** docker volume ls

**Output:**

DRIVER    VOLUME NAME
local     678f3c3ef32a8060a545d604f1a09e0112db9e2f2b644f01cc2a0f5d11ac28c5
local     cff3fc310cf5d819beee9ff449aeb749b1de6ff416c389a5dd99ce5875810deb
local     my_volume

**Step 2**

**Command:** docker run --name nginx-local -p 80:80 -v my_volume:/usr/share/nginx/html -d nginx

**Output:** 

Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
648e0aadf75a: Pull complete
262696647b70: Pull complete
e66d0270d23f: Pull complete
55ac49bd649c: Pull complete
cbf42f5a00d2: Pull complete
8015f365966b: Pull complete
4cadff8bc2aa: Pull complete
Digest: sha256:67f9a4f10d147a6e04629340e6493c9703300ca23a2f7f3aa56fe615d75d31ca
Status: Downloaded newer image for nginx:latest
c4015f9241bfdb5a8f3f672ffd3b5424fea82c3bc54a7a5c6adf46ee05168495


**Step 3**

**Command:** 127.0.0.0:80

**Output:** 

Welcome to nginx!
If you see this page, the nginx web server is successfully installed and working. Further configuration is required.

For online documentation and support please refer to nginx.org.
Commercial support is available at nginx.com.

Thank you for using nginx.



**Step 4**

**Command:** Done

**Step 5**

**Command:** docker cp index.html nginx_local:/usr/share/nginx/html

**Output:** Hello

**Step 6**

**Command:** docker cp index.html nginx_local:/usr/share/nginx/html

**Output:** Hello