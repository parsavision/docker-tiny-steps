# 🐳 Docker Tiny Steps: 600 Exercises for Complete Beginners

A complete, gradual learning path designed for absolute beginners.  Each exercise teaches exactly ONE concept with clear explanations.  No cloud services - everything runs locally! 

## How to Use This Guide
- ✅ = Complete
- 📝 = In Progress  
- ⭐ = Important Concept
- 🎯 = Practice This Multiple Times

---

## 🌟 PHASE 1: Understanding Docker Basics (Exercises 1-30)

### Week 1: What is Docker? 

**Exercise 1: Install Docker** ⭐✅  
**Goal:** Get Docker running on your computer  
**Task:** Download and install Docker Desktop (Windows/Mac) or Docker Engine (Linux)  
**Concept:** Docker is software that runs containers  
**Help:** Visit docker.com and follow installation instructions for your OS

**Exercise 2: Verify Installation**✅  
**Goal:** Confirm Docker is working  
**Task:** Open terminal and run `docker --version`  
**Concept:** Command line interface to Docker  
**Expected:** You should see version number like "Docker version 24.0.x"

**Exercise 3: Check Docker Status**✅  
**Goal:** Ensure Docker daemon is running  
**Task:** Run `docker info`  
**Concept:** Docker daemon runs in background  
**Help:** If error, start Docker Desktop or run `sudo systemctl start docker`

**Exercise 4: Your First Container** ⭐✅  
**Goal:** Run your very first container  
**Task:** Run `docker run hello-world`  
**Concept:** Containers are running instances of images  
**Help:** Docker will download the image automatically

**Exercise 5: Understand the Output**✅  
**Goal:** Read what just happened  
**Task:** Read the output from hello-world carefully  
**Concept:** Docker pulled image, created container, ran it, then exited  

**Exercise 6: List Running Containers**✅  
**Goal:** See what's currently running  
**Task:** Run `docker ps`  
**Concept:** `ps` shows running containers  
**Expected:** Empty list (hello-world already exited)

**Exercise 7: List All Containers** ⭐✅  
**Goal:** See all containers including stopped ones  
**Task:** Run `docker ps -a`  
**Concept:** `-a` flag shows all containers  
**Expected:** You'll see your hello-world container

**Exercise 8: Container ID**✅  
**Goal:** Understand container identification  
**Task:** Look at the CONTAINER ID column from `docker ps -a`  
**Concept:** Every container has unique ID  
**Note:** You can use first few characters of ID

**Exercise 9: Container Names**✅  
**Goal:** Understand container naming  
**Task:** Look at the NAMES column from `docker ps -a`  
**Concept:** Docker auto-generates funny names  
**Example:** "angry_einstein" or "happy_darwin"

**Exercise 10: Remove a Container**✅  
**Goal:** Clean up stopped containers  
**Task:** Run `docker rm <container_id or name>`  
**Concept:** Containers take disk space even when stopped  
**Help:** Use ID or name from previous exercise

---

### Week 2: Docker Images

**Exercise 11: List Images** ⭐✅  
**Goal:** See what images you have locally  
**Task:** Run `docker images`  
**Concept:** Images are templates for containers  
**Expected:** You should see hello-world image

**Exercise 12: Pull an Image** ✅ 
**Goal:** Download an image without running it  
**Task:** Run `docker pull alpine`  
**Concept:** `pull` downloads image from registry  
**Note:** alpine is a tiny Linux distribution

**Exercise 13: Check Image Size**  ✅
**Goal:** Understand image sizes vary  
**Task:** Run `docker images` and look at SIZE column  
**Concept:** Smaller images are faster to download  
**Compare:** hello-world vs alpine sizes

**Exercise 14: Pull Ubuntu Image**  ✅
**Goal:** Get a common base image  
**Task:** Run `docker pull ubuntu`  
**Concept:** Ubuntu is a popular base for many containers  

**Exercise 15: Compare Image Sizes**  
**Goal:** See difference between distributions  
**Task:** Compare alpine (~5MB) vs ubuntu (~77MB)  
**Concept:** Choose base images wisely for production  

**Exercise 16: Image Tags** ⭐ ✅ 
**Goal:** Understand image versions  
**Task:** Run `docker pull ubuntu:22.04`  
**Concept:** Tags specify image version (default is :latest)  
**Help:** Tag comes after colon

**Exercise 17: List Specific Tag** ✅ 
**Goal:** See tagged images  
**Task:** Run `docker images ubuntu`  
**Concept:** Filter images by name  
**Expected:** You may see multiple ubuntu versions

**Exercise 18: Remove an Image**  ✅
**Goal:** Clean up unused images  
**Task:** Run `docker rmi hello-world`  
**Concept:** `rmi` removes images  
**Warning:** Can't remove if containers exist using it

**Exercise 19: Force Remove Image** ✅ 
**Goal:** Remove image with existing containers  
**Task:** Run `docker rmi -f hello-world`  
**Concept:** `-f` forces removal  

**Exercise 20: Pull Nginx Image** ⭐ ✅
**Goal:** Get a web server image  
**Task:** Run `docker pull nginx`  
**Concept:** nginx is popular web server  
**Note:** We'll use this in many exercises

---

### Week 3: Running Containers

**Exercise 21: Run Alpine Container** ✅ 
**Goal:** Run a minimal Linux container  
**Task:** Run `docker run alpine`  
**Concept:** Container runs default command and exits  
**Expected:** Nothing visible happens

**Exercise 22: Run Command in Container** ⭐✅  
**Goal:** Execute specific command  
**Task:** Run `docker run alpine echo "Hello from container"`  
**Concept:** Override default command  
**Expected:** You see "Hello from container"

**Exercise 23: List Files in Container** ✅ 
**Goal:** Explore container filesystem  
**Task:** Run `docker run alpine ls /`  
**Concept:** Containers have their own filesystem  
**Expected:** You see Linux directory structure

**Exercise 24: Interactive Mode** ⭐✅  
**Goal:** Get inside a container  
**Task:** Run `docker run -it alpine /bin/sh`  
**Concept:** `-i` interactive, `-t` terminal  
**Help:** Type `exit` to leave

**Exercise 25: Explore Inside Container**✅  
**Goal:** Look around inside container  
**Task:** While inside alpine, run `ls`, `pwd`, `cat /etc/os-release`  
**Concept:** Container has isolated filesystem  
**Help:** You're in a mini Linux system! 

**Exercise 26: Check Container Hostname**✅  
**Goal:** See container's identity  
**Task:** Inside container, run `hostname`  
**Concept:** Each container has unique hostname (same as container ID)  

**Exercise 27: Container User** ✅ 
**Goal:** See who you are inside container  
**Task:** Run `whoami` inside container  
**Concept:** Default user is often root  
**Expected:** "root" in most cases

**Exercise 28: Exit Container** ⭐✅  
**Goal:** Leave interactive container  
**Task:** Type `exit` or press Ctrl+D  
**Concept:** Exiting stops the container  
**Note:** Container stops when main process ends

**Exercise 29: Run Ubuntu Interactive**✅  
**Goal:** Practice with another distribution  
**Task:** Run `docker run -it ubuntu bash`  
**Concept:** Ubuntu uses bash by default  

**Exercise 30: Install Package in Container** 📝✅  
**Goal:** Modify running container  
**Task:** Inside Ubuntu, run `apt update && apt install -y curl`  
**Concept:** You can install software inside container  
**Warning:** Changes lost when container is removed! 

---

## 🎯 PHASE 2: Container Lifecycle (Exercises 31-70)

### Week 4: Container States

**Exercise 31: Run in Background** ⭐✅  
**Goal:** Run container without blocking terminal  
**Task:** Run `docker run -d nginx`  
**Concept:** `-d` is detached mode  
**Expected:** Returns container ID

**Exercise 32: Verify Running Container**✅  
**Goal:** See container is running  
**Task:** Run `docker ps`  
**Concept:** Now you'll see nginx running  
**Note:** Shows STATUS as "Up X seconds"

**Exercise 33: Stop a Container** ⭐✅  
**Goal:** Gracefully stop running container  
**Task:** Run `docker stop <container_id>`  
**Concept:** Sends SIGTERM, waits, then SIGKILL  
**Help:** Use ID from `docker ps`

**Exercise 34: Start a Container** ⭐ ✅ 
**Goal:** Restart stopped container  
**Task:** Run `docker start <container_id>`  
**Concept:** Start previously stopped container  
**Note:** Container keeps its data

**Exercise 35: Restart a Container**✅  
**Goal:** Stop and start in one command  
**Task:** Run `docker restart <container_id>`  
**Concept:** Combines stop and start  

**Exercise 36: Kill a Container**✅  
**Goal:** Force stop immediately  
**Task:** Run `docker kill <container_id>`  
**Concept:** Sends SIGKILL (no grace period)  
**Warning:** Use only when stop doesn't work

**Exercise 37: Pause a Container**  
**Goal:** Freeze container processes  
**Task:** Run `docker pause <container_id>`  
**Concept:** Suspends all processes  

**Exercise 38: Unpause a Container**  
**Goal:** Resume paused container  
**Task:** Run `docker unpause <container_id>`  
**Concept:** Processes continue from where they stopped  

**Exercise 39: Container Logs** ⭐  
**Goal:** See container output  
**Task:** Run `docker logs <container_id>`  
**Concept:** View stdout/stderr from container  

**Exercise 40: Follow Logs**  
**Goal:** Watch logs in real-time  
**Task:** Run `docker logs -f <container_id>`  
**Concept:** `-f` follows like `tail -f`  
**Help:** Ctrl+C to stop following

---

### Week 5: Container Naming & Management

**Exercise 41: Name Your Container** ⭐  
**Goal:** Give container custom name  
**Task:** Run `docker run -d --name my-nginx nginx`  
**Concept:** `--name` sets container name  
**Benefit:** Easier to reference than random ID

**Exercise 42: Use Container Name**  
**Goal:** Reference container by name  
**Task:** Run `docker stop my-nginx`  
**Concept:** Names work everywhere IDs work  

**Exercise 43: Rename Container**  
**Goal:** Change container name  
**Task:** Run `docker rename my-nginx webserver`  
**Concept:** Container names can be changed  

**Exercise 44: Remove Running Container Error**  
**Goal:** Understand rm protection  
**Task:** Try `docker rm webserver` (will error!)  
**Concept:** Can't remove running container by default  

**Exercise 45: Force Remove Running Container** ⭐  
**Goal:** Remove running container  
**Task:** Run `docker rm -f webserver`  
**Concept:** `-f` stops then removes  

**Exercise 46: Auto Remove Container** ⭐  
**Goal:** Cleanup automatically  
**Task:** Run `docker run --rm alpine echo "temporary"`  
**Concept:** `--rm` removes container after exit  
**Use case:** Testing, one-off commands

**Exercise 47: Run and Remove Practice**  
**Goal:** Practice auto-removal  
**Task:** Run `docker run --rm -it ubuntu bash`, then exit  
**Concept:** Container disappears after exit  
**Verify:** `docker ps -a` won't show it

**Exercise 48: Remove All Stopped Containers** ⭐  
**Goal:** Clean up multiple containers  
**Task:** Run `docker container prune`  
**Concept:** Removes all stopped containers  
**Warning:** Confirm with 'y' when prompted

**Exercise 49: Container Stats**  
**Goal:** See resource usage  
**Task:** Run `docker stats`  
**Concept:** Live CPU, memory, network stats  
**Help:** Ctrl+C to exit

**Exercise 50: Inspect Container** ⭐  
**Goal:** Get detailed container info  
**Task:** Run `docker inspect <container_id>`  
**Concept:** Returns JSON with all details  
**Note:** Shows IP, mounts, config, etc.

---

### Week 6: Executing Commands

**Exercise 51: Exec into Running Container** ⭐  
**Goal:** Run command in running container  
**Task:** Start nginx, then `docker exec -it <id> bash`  
**Concept:** `exec` runs in existing container  
**Difference:** Unlike `run`, container already exists

**Exercise 52: Non-interactive Exec**  
**Goal:** Run single command  
**Task:** `docker exec <container_id> cat /etc/nginx/nginx.conf`  
**Concept:** Execute and get output  

**Exercise 53: Exec as Different User**  
**Goal:** Run command as specific user  
**Task:** `docker exec -u www-data <id> whoami`  
**Concept:** `-u` specifies user  

**Exercise 54: View Container Processes**  
**Goal:** See what's running inside  
**Task:** `docker exec <id> ps aux`  
**Concept:** Container runs isolated processes  

**Exercise 55: Check Container Environment**  
**Goal:** See environment variables  
**Task:** `docker exec <id> env`  
**Concept:** Containers have their own environment  

**Exercise 56: Create File in Container**  
**Goal:** Modify container via exec  
**Task:** `docker exec <id> touch /tmp/myfile`  
**Concept:** Changes persist while container runs  

**Exercise 57: Verify File Exists**  
**Goal:** Confirm previous change  
**Task:** `docker exec <id> ls /tmp/`  
**Concept:** Container state persists during runtime  

**Exercise 58: Attach to Container** ⭐  
**Goal:** Connect to main process  
**Task:** `docker attach <container_id>`  
**Concept:** Attach to stdin/stdout of main process  
**Warning:** Ctrl+C may stop container! 

**Exercise 59: Detach from Container**  
**Goal:** Leave without stopping  
**Task:** Press Ctrl+P then Ctrl+Q  
**Concept:** Detach sequence keeps container running  

**Exercise 60: Top Command**  
**Goal:** See processes without exec  
**Task:** `docker top <container_id>`  
**Concept:** View processes from outside container  

---

### Week 7: Container Copy & Export

**Exercise 61: Copy File to Container** ⭐  
**Goal:** Transfer file into container  
**Task:** Create local file, then `docker cp myfile. txt <id>:/tmp/`  
**Concept:** `cp` copies between host and container  
**Help:** First create: `echo "hello" > myfile.txt`

**Exercise 62: Copy File from Container** ⭐  
**Goal:** Extract file from container  
**Task:** `docker cp <id>:/etc/nginx/nginx. conf ./`  
**Concept:** Works in both directions  

**Exercise 63: Copy Directory**  
**Goal:** Copy entire folder  
**Task:** `docker cp <id>:/etc/nginx/ ./nginx-config/`  
**Concept:** Directories copy recursively  

**Exercise 64: Export Container Filesystem**  
**Goal:** Save container as tar  
**Task:** `docker export <id> > container.tar`  
**Concept:** Exports filesystem, not image  

**Exercise 65: View Export Contents**  
**Goal:** See what was exported  
**Task:** `tar -tf container.tar | head -20`  
**Concept:** It's a complete filesystem  

**Exercise 66: Import as Image**  
**Goal:** Create image from export  
**Task:** `docker import container. tar my-imported-image`  
**Concept:** Creates new image from filesystem  

**Exercise 67: Save Image** ⭐  
**Goal:** Save image to file  
**Task:** `docker save nginx > nginx.tar`  
**Concept:** Saves image with layers and metadata  
**Difference:** `save` for images, `export` for containers

**Exercise 68: Load Image** ⭐  
**Goal:** Load image from file  
**Task:** `docker load < nginx.tar`  
**Concept:** Restore image on another machine  
**Use case:** Offline transfer, backup

**Exercise 69: Diff Container**  
**Goal:** See filesystem changes  
**Task:** `docker diff <container_id>`  
**Concept:** Shows added/changed/deleted files  
**Legend:** A=Added, C=Changed, D=Deleted

**Exercise 70: Commit Container** 📝 ⭐  
**Goal:** Create image from container  
**Task:** `docker commit <id> my-custom-image`  
**Concept:** Saves container state as new image  
**Note:** Not recommended for production (use Dockerfile)

---

## 🔨 PHASE 3: Port Mapping & Networking (Exercises 71-110)

### Week 8: Port Basics

**Exercise 71: Run Nginx with Port** ⭐  
**Goal:** Access web server from browser  
**Task:** `docker run -d -p 8080:80 nginx`  
**Concept:** `-p hostPort:containerPort`  
**Test:** Open http://localhost:8080 in browser

**Exercise 72: Understand Port Mapping**  
**Goal:** Grasp what just happened  
**Task:** Think about 8080:80 meaning  
**Concept:** Host port 8080 forwards to container port 80  
**Analogy:** Like forwarding calls to different extension

**Exercise 73: Different Host Port**  
**Goal:** Use any available port  
**Task:** `docker run -d -p 9090:80 --name web2 nginx`  
**Concept:** Host port can be anything available  
**Test:** Open http://localhost:9090

**Exercise 74: Multiple Port Mappings**  
**Goal:** Expose multiple ports  
**Task:** `docker run -d -p 8080:80 -p 8443:443 nginx`  
**Concept:** Use multiple `-p` flags  

**Exercise 75: Random Host Port** ⭐  
**Goal:** Let Docker choose port  
**Task:** `docker run -d -p 80 nginx`  
**Concept:** Docker assigns random available port  
**Check:** `docker ps` shows mapped port

**Exercise 76: Find Container Port**  
**Goal:** See port mappings  
**Task:** `docker port <container_id>`  
**Concept:** Lists all port mappings  

**Exercise 77: Bind to Specific IP**  
**Goal:** Limit which IP accepts connections  
**Task:** `docker run -d -p 127.0.0. 1:8080:80 nginx`  
**Concept:** Only localhost can connect  
**Security:** Prevents external access

**Exercise 78: Expose All Ports**  
**Goal:** Publish all exposed ports  
**Task:** `docker run -d -P nginx`  
**Concept:** `-P` (uppercase) publishes all EXPOSE ports  

**Exercise 79: Run Python Web Server**  
**Goal:** Try another web service  
**Task:** `docker run -d -p 8000:8000 python:3 python -m http.server`  
**Concept:** Any program can listen on ports  
**Test:** Open http://localhost:8000

**Exercise 80: Check What's Listening**  
**Goal:** Verify port inside container  
**Task:** `docker exec <id> netstat -tlnp` or `ss -tlnp`  
**Concept:** Container has its own network stack  

---

### Week 9: Docker Networks

**Exercise 81: List Networks** ⭐  
**Goal:** See default networks  
**Task:** `docker network ls`  
**Concept:** Docker has built-in networks  
**Expected:** bridge, host, none

**Exercise 82: Inspect Bridge Network**  
**Goal:** Understand default network  
**Task:** `docker network inspect bridge`  
**Concept:** Containers connect to bridge by default  

**Exercise 83: Create Custom Network** ⭐  
**Goal:** Make your own network  
**Task:** `docker network create mynetwork`  
**Concept:** Custom networks have better DNS  

**Exercise 84: Run Container on Network**  
**Goal:** Attach to specific network  
**Task:** `docker run -d --name web --network mynetwork nginx`  
**Concept:** `--network` specifies network  

**Exercise 85: Another Container Same Network**  
**Goal:** Create second container  
**Task:** `docker run -d --name db --network mynetwork redis`  
**Concept:** Containers on same network can communicate  

**Exercise 86: Container DNS** ⭐  
**Goal:** Containers resolve each other by name  
**Task:** `docker exec web ping db`  
**Concept:** Container names work as hostnames  
**Note:** Only works on custom networks, not bridge! 

**Exercise 87: Connect to Network**  
**Goal:** Add running container to network  
**Task:** `docker network connect mynetwork <container_id>`  
**Concept:** Containers can join networks after starting  

**Exercise 88: Disconnect from Network**  
**Goal:** Remove from network  
**Task:** `docker network disconnect mynetwork <container_id>`  
**Concept:** Remove network access  

**Exercise 89: Container IP Address**  
**Goal:** Find container's IP  
**Task:** `docker inspect -f '{{range. NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <id>`  
**Concept:** Each container gets IP on network  

**Exercise 90: Host Network Mode** ⭐  
**Goal:** Use host's network directly  
**Task:** `docker run --network host nginx`  
**Concept:** No network isolation, uses host ports  
**Note:** Linux only, not Mac/Windows

---

### Week 10: Advanced Networking

**Exercise 91: None Network**  
**Goal:** Run container without network  
**Task:** `docker run --network none alpine ip addr`  
**Concept:** Complete network isolation  
**Use case:** Security-sensitive containers

**Exercise 92: Network Aliases**  
**Goal:** Give container multiple names  
**Task:** `docker run --network mynetwork --network-alias webserver nginx`  
**Concept:** Additional DNS names for container  

**Exercise 93: Multiple Aliases**  
**Goal:** Add more aliases  
**Task:** `docker run --network mynet --network-alias web --network-alias frontend nginx`  
**Concept:** Container responds to multiple names  

**Exercise 94: Inspect Container Network**  
**Goal:** See network details  
**Task:** `docker inspect <id> | grep -A 20 "Networks"`  
**Concept:** View IP, gateway, network name  

**Exercise 95: Remove Network**  
**Goal:** Delete custom network  
**Task:** `docker network rm mynetwork`  
**Concept:** Must disconnect all containers first  
**Error:** Will fail if containers connected

**Exercise 96: Prune Networks**  
**Goal:** Remove unused networks  
**Task:** `docker network prune`  
**Concept:** Removes networks not in use  

**Exercise 97: Container to Container via IP**  
**Goal:** Connect using IP address  
**Task:** Find IP with inspect, ping from another container  
**Concept:** Direct IP works but less flexible  
**Note:** IPs can change!

**Exercise 98: Test Web from Another Container**  
**Goal:** HTTP request between containers  
**Task:** `docker exec <alpine-id> wget -qO- http://web:80`  
**Concept:** Service discovery via DNS  

**Exercise 99: Publish to Specific Interface**  
**Goal:** Fine-grained port control  
**Task:** `docker run -p 192.168.1. 100:8080:80 nginx`  
**Concept:** Bind to specific host interface  

**Exercise 100: Network Troubleshooting** 📝  
**Goal:** Debug network issues  
**Task:** Practice: `ping`, `curl`, `wget`, `nslookup` inside containers  
**Concept:** Standard Linux tools work  
**Help:** May need to install tools first

---

### Week 11: Linking & Service Communication

**Exercise 101: Legacy Link (Deprecated)**  
**Goal:** Understand old linking method  
**Task:** `docker run --link db:database alpine env`  
**Concept:** `--link` is deprecated, use networks  
**Note:** Still works but not recommended

**Exercise 102: Environment from Link**  
**Goal:** See link variables  
**Task:** Check environment variables from linked container  
**Concept:** Link creates env vars with connection info  

**Exercise 103: DNS in Custom Network** ⭐  
**Goal:** Confirm DNS works  
**Task:** `docker exec <container> nslookup <other-container>`  
**Concept:** Docker's embedded DNS server  

**Exercise 104: Add to /etc/hosts**  
**Goal:** Custom host entries  
**Task:** `docker run --add-host myhost:10.0.0. 1 alpine cat /etc/hosts`  
**Concept:** Add custom DNS entries  

**Exercise 105: Set Container Hostname**  
**Goal:** Custom hostname  
**Task:** `docker run -h mywebserver nginx hostname`  
**Concept:** `-h` or `--hostname` sets hostname  

**Exercise 106: Set DNS Server**  
**Goal:** Custom DNS server  
**Task:** `docker run --dns 8.8.8.8 alpine cat /etc/resolv.conf`  
**Concept:** Override default DNS  

**Exercise 107: DNS Search Domain**  
**Goal:** Custom search domain  
**Task:** `docker run --dns-search example.com alpine cat /etc/resolv.conf`  
**Concept:** Append domain to lookups  

**Exercise 108: Internal Network**  
**Goal:** Network without external access  
**Task:** `docker network create --internal isolated`  
**Concept:** Containers can talk, but not internet  

**Exercise 109: Test Internal Network**  
**Goal:** Verify no external access  
**Task:** Run container on internal network, try to ping google. com  
**Concept:** Should fail - that's expected!   

**Exercise 110: Network Driver Bridge** 📝  
**Goal:** Understand default driver  
**Task:** `docker network create --driver bridge mybridge`  
**Concept:** Bridge is default, good for single host  

---

## 📦 PHASE 4: Volumes & Data Persistence (Exercises 111-160)

### Week 12: Volume Basics

**Exercise 111: Data Loss Demo** ⭐  
**Goal:** See why volumes matter  
**Task:** Run container, create file, remove container, run again - file gone!   
**Concept:** Container filesystem is ephemeral  
**Learning:** Data needs to be persisted!

**Exercise 112: Create Named Volume** ⭐  
**Goal:** Create persistent storage  
**Task:** `docker volume create mydata`  
**Concept:** Volumes live outside containers  

**Exercise 113: List Volumes**  
**Goal:** See all volumes  
**Task:** `docker volume ls`  
**Concept:** Volumes persist independently  

**Exercise 114: Inspect Volume**  
**Goal:** Get volume details  
**Task:** `docker volume inspect mydata`  
**Concept:** Shows mountpoint on host  

**Exercise 115: Mount Volume to Container** ⭐  
**Goal:** Use volume in container  
**Task:** `docker run -v mydata:/data alpine touch /data/hello`  
**Concept:** `-v volumeName:containerPath`  

**Exercise 116: Verify Data Persists** ⭐  
**Goal:** Confirm persistence  
**Task:** `docker run -v mydata:/data alpine ls /data`  
**Concept:** New container sees old data  
**Expected:** "hello" file exists! 

**Exercise 117: Share Volume Between Containers**  
**Goal:** Multiple containers, same data  
**Task:** Run two containers with same volume  
**Concept:** Volumes enable data sharing  

**Exercise 118: Concurrent Access**  
**Goal:** See live sharing  
**Task:** Container A writes, Container B reads  
**Concept:** Changes visible immediately  

**Exercise 119: Remove Volume**  
**Goal:** Delete volume  
**Task:** `docker volume rm mydata`  
**Concept:** Must not be in use  
**Warning:** Data is permanently deleted!

**Exercise 120: Prune Volumes**  
**Goal:** Remove unused volumes  
**Task:** `docker volume prune`  
**Concept:** Cleans up orphaned volumes  

---

### Week 13: Bind Mounts

**Exercise 121: Bind Mount Basics** ⭐  
**Goal:** Mount host directory  
**Task:** `docker run -v /path/on/host:/path/in/container alpine ls /path/in/container`  
**Concept:** Direct host filesystem access  
**Help:** Use absolute path or `$(pwd)`

**Exercise 122: Current Directory Mount** ⭐  
**Goal:** Mount current folder  
**Task:** `docker run -v $(pwd):/app alpine ls /app`  
**Concept:** `$(pwd)` gives current directory  
**Windows:** Use `${PWD}` in PowerShell

**Exercise 123: Create File from Container**  
**Goal:** Container writes to host  
**Task:** Mount folder, create file inside, check host  
**Concept:** Changes go both directions  

**Exercise 124: Edit on Host**  
**Goal:** Host changes visible in container  
**Task:** Edit file on host, see in container  
**Concept:** Live synchronization  
**Use case:** Development workflow

**Exercise 125: Read-Only Mount** ⭐  
**Goal:** Prevent container from writing  
**Task:** `docker run -v $(pwd):/app:ro alpine touch /app/test`  
**Concept:** `:ro` makes mount read-only  
**Expected:** Error - read-only filesystem

**Exercise 126: Mount Specific File**  
**Goal:** Mount single file, not directory  
**Task:** `docker run -v $(pwd)/config.txt:/etc/config.txt:ro alpine cat /etc/config.txt`  
**Concept:** Can mount individual files  

**Exercise 127: Development Server** 📝  
**Goal:** Hot-reload development  
**Task:** Mount source code, run dev server  
**Concept:** Edit code on host, server reloads  
**Example:** Node.js, Python, etc.

**Exercise 128: Override Container Files**  
**Goal:** Replace container content  
**Task:** Mount your HTML to nginx's html folder  
**Concept:** Bind mount "hides" container content  

**Exercise 129: Nginx Custom Content** ⭐  
**Goal:** Serve your own files  
**Task:** `docker run -v $(pwd)/html:/usr/share/nginx/html:ro -p 8080:80 nginx`  
**Concept:** Custom website in container  

**Exercise 130: Database Data Directory**  
**Goal:** Persist database  
**Task:** Mount volume to database data directory  
**Concept:** DB data survives container restart  

---

### Week 14: Advanced Volume Usage

**Exercise 131: tmpfs Mount**  
**Goal:** In-memory storage  
**Task:** `docker run --tmpfs /app:rw,size=100m alpine df -h /app`  
**Concept:** Data in RAM, not disk  
**Use case:** Sensitive data, speed

**Exercise 132: Volume with New Syntax** ⭐  
**Goal:** Use --mount flag  
**Task:** `docker run --mount source=mydata,target=/data alpine ls /data`  
**Concept:** `--mount` is more explicit than `-v`  
**Benefit:** Clearer, more options

**Exercise 133: Mount Type Volume**  
**Goal:** Explicit volume mount  
**Task:** `docker run --mount type=volume,source=vol,target=/data alpine`  
**Concept:** type=volume for named volumes  

**Exercise 134: Mount Type Bind**  
**Goal:** Explicit bind mount  
**Task:** `docker run --mount type=bind,source=$(pwd),target=/app alpine`  
**Concept:** type=bind for host paths  

**Exercise 135: Anonymous Volume**  
**Goal:** Volume without name  
**Task:** `docker run -v /data alpine touch /data/file`  
**Concept:** Docker creates random name  
**Note:** Harder to find later! 

**Exercise 136: Find Anonymous Volume**  
**Goal:** Locate unnamed volume  
**Task:** `docker inspect <container> | grep -A 5 Mounts`  
**Concept:** Volume info in container metadata  

**Exercise 137: Volume Driver**  
**Goal:** Understand volume drivers  
**Task:** `docker volume create --driver local myvol`  
**Concept:** Local is default, others exist  
**Note:** NFS, cloud drivers, etc.

**Exercise 138: Volume Labels**  
**Goal:** Tag volumes  
**Task:** `docker volume create --label project=myapp datavol`  
**Concept:** Labels help organization  

**Exercise 139: Filter Volumes by Label**  
**Goal:** Find labeled volumes  
**Task:** `docker volume ls --filter label=project=myapp`  
**Concept:** Search by metadata  

**Exercise 140: Backup Volume** ⭐ 📝  
**Goal:** Copy volume data  
**Task:** `docker run --rm -v mydata:/data -v $(pwd):/backup alpine tar cvf /backup/backup.tar /data`  
**Concept:** Mount volume + bind mount to copy out  
**Important:** Essential for data safety!

---

### Week 15: Volume Use Cases

**Exercise 141: Restore Volume**  
**Goal:** Restore from backup  
**Task:** `docker run --rm -v newdata:/data -v $(pwd):/backup alpine tar xvf /backup/backup.tar -C /`  
**Concept:** Reverse of backup process  

**Exercise 142: MySQL with Volume** ⭐  
**Goal:** Persistent database  
**Task:** `docker run -v mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secret mysql`  
**Concept:** Database files persist  

**Exercise 143: PostgreSQL with Volume**  
**Goal:** Another database example  
**Task:** `docker run -v pg-data:/var/lib/postgresql/data -e POSTGRES_PASSWORD=secret postgres`  
**Concept:** Same pattern, different DB  

**Exercise 144: Redis with Volume**  
**Goal:** Persist Redis data  
**Task:** `docker run -v redis-data:/data redis redis-server --appendonly yes`  
**Concept:** Enable persistence + volume  

**Exercise 145: Configuration Volume**  
**Goal:** External config files  
**Task:** Mount config file into container  
**Concept:** Separate config from image  

**Exercise 146: Log Volume**  
**Goal:** Persist application logs  
**Task:** Mount volume to log directory  
**Concept:** Logs survive container restart  

**Exercise 147: Shared Cache Volume**  
**Goal:** Share build cache  
**Task:** Multiple containers share cache volume  
**Concept:** Speed up builds  
**Example:** npm, pip cache

**Exercise 148: WordPress with Volumes**  
**Goal:** Real-world multi-volume  
**Task:** WordPress with separate DB and uploads volumes  
**Concept:** Different data types, different volumes  

**Exercise 149: Volume from Another Container**  
**Goal:** Copy volumes-from pattern  
**Task:** `docker run --volumes-from container1 alpine ls`  
**Concept:** Share volumes between containers  

**Exercise 150: Check Volume Disk Usage** 📝  
**Goal:** Monitor volume size  
**Task:** `docker system df -v`  
**Concept:** See space used by volumes  

---

### Week 16: Permission & Ownership

**Exercise 151: Volume Permission Issue** ⭐  
**Goal:** Understand common problem  
**Task:** Mount volume, see permission denied  
**Concept:** Container user vs host user  

**Exercise 152: Run as Specific User**  
**Goal:** Match host user  
**Task:** `docker run -u $(id -u):$(id -g) -v $(pwd):/app alpine touch /app/test`  
**Concept:** `-u` sets user ID  

**Exercise 153: Check File Owner**  
**Goal:** See ownership difference  
**Task:** Create file in container as root, check owner on host  
**Concept:** Root in container = root on host  

**Exercise 154: Fix Permission with chown**  
**Goal:** Change ownership  
**Task:** `docker exec <id> chown -R 1000:1000 /data`  
**Concept:** Adjust permissions to match  

**Exercise 155: Read-Only Container** ⭐  
**Goal:** Immutable container  
**Task:** `docker run --read-only alpine touch /file`  
**Concept:** Cannot write to container filesystem  
**Expected:** Error - read-only

**Exercise 156: Read-Only with tmpfs**  
**Goal:** Writable temp space  
**Task:** `docker run --read-only --tmpfs /tmp alpine touch /tmp/ok`  
**Concept:** Combine for security + function  

**Exercise 157: Read-Only with Volume**  
**Goal:** Persist specific directory  
**Task:** `docker run --read-only -v data:/data alpine touch /data/ok`  
**Concept:** Volume is writable, rest is not  

**Exercise 158: Userns Remap (Preview)**  
**Goal:** Understand user namespaces  
**Task:** Read about `userns-remap` in Docker docs  
**Concept:** Map root in container to non-root on host  
**Note:** Advanced security feature

**Exercise 159: Nocopy Option**  
**Goal:** Don't copy volume content  
**Task:** `docker run --mount source=vol,target=/data,nocopy alpine`  
**Concept:** Skip copying container path to volume  

**Exercise 160: Best Practices Review** 📝  
**Goal:** Summary of volume patterns  
**Task:** List when to use: named volumes, bind mounts, tmpfs  
**Concept:** Right tool for right job  
**Pattern:** DB→volume, code→bind, secrets→tmpfs

---

## 🏗️ PHASE 5: Dockerfile Basics (Exercises 161-220)

### Week 17: First Dockerfile

**Exercise 161: Create Dockerfile** ⭐  
**Goal:** Write first Dockerfile  
**Task:** Create file named `Dockerfile` with `FROM alpine`  
**Concept:** Dockerfile defines image  
**Note:** No file extension! 

**Exercise 162: FROM Instruction** ⭐  
**Goal:** Understand base image  
**Task:** `FROM alpine:3.18`  
**Concept:** Every Dockerfile starts with FROM  
**Rule:** Must be first instruction

**Exercise 163: Build Image** ⭐  
**Goal:** Create image from Dockerfile  
**Task:** `docker build -t myfirstimage . `  
**Concept:** `-t` names/tags the image  
**Note:** `. ` means current directory

**Exercise 164: Verify Built Image**  
**Goal:** See your new image  
**Task:** `docker images myfirstimage`  
**Concept:** Image exists locally now  

**Exercise 165: Run Your Image**  
**Goal:** Create container from image  
**Task:** `docker run myfirstimage`  
**Concept:** Same as any other image  

**Exercise 166: RUN Instruction** ⭐  
**Goal:** Execute command during build  
**Task:** Add `RUN echo "Hello"` to Dockerfile  
**Concept:** RUN executes at build time  

**Exercise 167: Install Package**  
**Goal:** Add software to image  
**Task:** `RUN apk add --no-cache curl`  
**Concept:** Modify filesystem in image  
**Note:** apk is Alpine's package manager

**Exercise 168: Multiple RUN Commands**  
**Goal:** Several RUN instructions  
**Task:** Add two RUN lines  
**Concept:** Each RUN creates new layer  
**Warning:** More layers = larger image

**Exercise 169: Combine RUN Commands** ⭐  
**Goal:** Optimize layers  
**Task:** `RUN apk add --no-cache curl wget && rm -rf /var/cache/apk/*`  
**Concept:** Use && to combine commands  
**Benefit:** Smaller image, fewer layers

**Exercise 170: CMD Instruction** ⭐  
**Goal:** Set default command  
**Task:** `CMD ["echo", "Hello World"]`  
**Concept:** CMD runs when container starts  
**Note:** Can be overridden at runtime

---

### Week 18: More Dockerfile Instructions

**Exercise 171: CMD vs RUN**  
**Goal:** Understand difference  
**Task:** RUN = build time, CMD = run time  
**Concept:** RUN modifies image, CMD runs container  

**Exercise 172: WORKDIR Instruction** ⭐  
**Goal:** Set working directory  
**Task:** `WORKDIR /app`  
**Concept:** All following commands run here  
**Benefit:** Cleaner than `cd` commands

**Exercise 173: COPY Instruction** ⭐  
**Goal:** Copy files into image  
**Task:** `COPY hello.txt /app/`  
**Concept:** Copy from build context to image  
**Help:** Create hello.txt first

**Exercise 174: Copy Multiple Files**  
**Goal:** Copy several files  
**Task:** `COPY file1. txt file2.txt /app/`  
**Concept:** Multiple sources, one destination  

**Exercise 175: Copy Directory**  
**Goal:** Copy entire folder  
**Task:** `COPY src/ /app/src/`  
**Concept:** Copies contents of directory  

**Exercise 176: COPY with Wildcard**  
**Goal:** Pattern matching  
**Task:** `COPY *.txt /app/`  
**Concept:** Glob patterns work  

**Exercise 177: ADD Instruction**  
**Goal:** Enhanced copy  
**Task:** `ADD archive.tar.gz /app/`  
**Concept:** ADD can extract archives  
**Note:** COPY is preferred for simple copies

**Exercise 178: EXPOSE Instruction** ⭐  
**Goal:** Document ports  
**Task:** `EXPOSE 8080`  
**Concept:** Tells Docker which ports to expose  
**Note:** Doesn't actually publish port!

**Exercise 179: ENV Instruction** ⭐  
**Goal:** Set environment variable  
**Task:** `ENV APP_ENV=production`  
**Concept:** Available at build and run time  

**Exercise 180: Use ENV Variable**  
**Goal:** Reference environment variable  
**Task:** `RUN echo $APP_ENV` or `CMD echo $APP_ENV`  
**Concept:** Variables expand in instructions  

---

### Week 19: Building Real Applications

**Exercise 181: Simple Web App** 📝 ⭐  
**Goal:** Create web application image  
**Task:** Dockerfile with nginx + custom HTML  
**Concept:** Real-world Dockerfile  
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
EXPOSE 80
```

**Exercise 182: Python Application**  
**Goal:** Build Python app image  
**Task:** FROM python, COPY script, CMD python  
**Concept:** Different base, same pattern  

**Exercise 183: ENTRYPOINT Instruction** ⭐  
**Goal:** Fixed command, variable args  
**Task:** `ENTRYPOINT ["python", "app.py"]`  
**Concept:** Can't be overridden easily  
**Difference:** ENTRYPOINT + CMD combine

**Exercise 184: ENTRYPOINT + CMD**  
**Goal:** Default arguments  
**Task:** `ENTRYPOINT ["echo"]` + `CMD ["default text"]`  
**Concept:** CMD provides default args to ENTRYPOINT  

**Exercise 185: Override ENTRYPOINT**  
**Goal:** Runtime override  
**Task:** `docker run --entrypoint /bin/sh image`  
**Concept:** `--entrypoint` overrides  

**Exercise 186: ARG Instruction** ⭐  
**Goal:** Build-time variables  
**Task:** `ARG VERSION=1.0`  
**Concept:** Only available during build  
**Usage:** `docker build --build-arg VERSION=2.0`

**Exercise 187: Use ARG in Dockerfile**  
**Goal:** Reference build argument  
**Task:** `RUN echo "Version: $VERSION"`  
**Concept:** Customize builds  

**Exercise 188: ARG vs ENV**  
**Goal:** Understand difference  
**Task:** ARG = build only, ENV = build + run  
**Concept:** ARG for build customization  
**Pattern:** `ARG VERSION` then `ENV VERSION=$VERSION`

**Exercise 189: LABEL Instruction**  
**Goal:** Add metadata  
**Task:** `LABEL maintainer="you@email.com" version="1.0"`  
**Concept:** Image metadata  
**View:** `docker inspect` shows labels

**Exercise 190: USER Instruction** ⭐  
**Goal:** Run as non-root  
**Task:** `RUN adduser -D myuser` then `USER myuser`  
**Concept:** Security best practice  

---

### Week 20: Dockerfile Best Practices

**Exercise 191: Order Matters** ⭐  
**Goal:** Understand layer caching  
**Task:** Put rarely-changing instructions first  
**Concept:** Docker caches unchanged layers  
**Order:** FROM → install deps → copy code → CMD

**Exercise 192: . dockerignore File** ⭐  
**Goal:** Exclude files from build  
**Task:** Create `. dockerignore` with `node_modules`, `. git`  
**Concept:** Faster builds, smaller context  
**Syntax:** Same as .gitignore

**Exercise 193: Minimize Layers**  
**Goal:** Reduce image size  
**Task:** Combine RUN commands  
**Concept:** Each instruction = one layer  

**Exercise 194: Clean Up in Same Layer**  
**Goal:** Remove temp files  
**Task:** Install package AND clean up in one RUN  
**Concept:** Can't remove in later layer  
**Example:** `RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*`

**Exercise 195: Use Specific Tags** ⭐  
**Goal:** Reproducible builds  
**Task:** `FROM python:3.11-slim` not `FROM python`  
**Concept:** `:latest` changes unexpectedly  

**Exercise 196: Multi-Stage Build Intro** ⭐  
**Goal:** Smaller final images  
**Task:** Build in one stage, copy to another  
**Concept:** Build tools not in final image  
```dockerfile
FROM node:18 AS builder
# build steps
FROM node:18-slim
COPY --from=builder /app/dist /app
```

**Exercise 197: Multi-Stage Build Practice**  
**Goal:** Go application build  
**Task:** Build Go app, copy binary only  
**Concept:** Huge size reduction  

**Exercise 198: COPY --from** ⭐  
**Goal:** Copy from previous stage  
**Task:** `COPY --from=builder /app/binary /app/`  
**Concept:** Reference stages by name  

**Exercise 199: Build Specific Stage**  
**Goal:** Target specific stage  
**Task:** `docker build --target builder -t myimage-builder .`  
**Concept:** Useful for debugging  

**Exercise 200: HEALTHCHECK Instruction** ⭐  
**Goal:** Container health monitoring  
**Task:** `HEALTHCHECK CMD curl -f http://localhost/ || exit 1`  
**Concept:** Docker checks if container healthy  
**View:** `docker ps` shows health status

---

### Week 21: Advanced Dockerfile

**Exercise 201: HEALTHCHECK Options**  
**Goal:** Configure health check  
**Task:** `HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD ... `  
**Concept:** Tune check frequency  

**Exercise 202: SHELL Instruction**  
**Goal:** Change default shell  
**Task:** `SHELL ["/bin/bash", "-c"]`  
**Concept:** Use bash instead of sh  

**Exercise 203: STOPSIGNAL Instruction**  
**Goal:** Custom stop signal  
**Task:** `STOPSIGNAL SIGQUIT`  
**Concept:** Graceful shutdown handling  

**Exercise 204: ONBUILD Instruction**  
**Goal:** Trigger in child builds  
**Task:** `ONBUILD COPY . /app`  
**Concept:** Runs when image is used as base  
**Use case:** Base images for team

**Exercise 205: Build with No Cache**  
**Goal:** Force fresh build  
**Task:** `docker build --no-cache -t myimage . `  
**Concept:** Ignore cached layers  
**Use case:** Debugging, fresh packages

**Exercise 206: Build with Build Args**  
**Goal:** Pass build-time values  
**Task:** `docker build --build-arg VERSION=2.0 -t myimage .`  
**Concept:** Customize without editing Dockerfile  

**Exercise 207: Dockerfile for Node.js** 📝 ⭐  
**Goal:** Best practice Node image  
**Task:** 
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . . 
EXPOSE 3000
CMD ["node", "server.js"]
```
**Concept:** Dependencies first, code second

**Exercise 208: Dockerfile for Python** 📝  
**Goal:** Best practice Python image  
**Task:** Similar pattern with pip  
**Concept:** requirements.txt before code  

**Exercise 209: Dockerfile for Go** 📝  
**Goal:** Minimal Go image  
**Task:** Multi-stage with scratch  
**Concept:** Final image can be < 10MB  

**Exercise 210: Build Context Understanding**  
**Goal:** What gets sent to daemon  
**Task:** Watch "Sending build context" message  
**Concept:** Entire directory sent unless ignored  

---

### Week 22: Image Optimization

**Exercise 211: Check Image Size**  
**Goal:** Analyze image size  
**Task:** `docker images myimage` or `docker history myimage`  
**Concept:** See layer sizes  

**Exercise 212: Use Slim Base Images** ⭐  
**Goal:** Reduce size  
**Task:** Compare `python:3. 11` vs `python:3.11-slim`  
**Concept:** Slim = fewer packages  

**Exercise 213: Alpine Base Images** ⭐  
**Goal:** Minimal Linux  
**Task:** Use `python:3.11-alpine`  
**Concept:** Alpine is ~5MB  
**Warning:** May have compatibility issues

**Exercise 214: Distroless Images**  
**Goal:** No OS at all  
**Task:** `FROM gcr.io/distroless/python3`  
**Concept:** Only your app, nothing else  
**Security:** Minimal attack surface

**Exercise 215: Scratch Image**  
**Goal:** Empty base  
**Task:** `FROM scratch` with static binary  
**Concept:** Smallest possible image  
**Use case:** Go, Rust binaries

**Exercise 216: Layer Analysis** ⭐  
**Goal:** See what's in layers  
**Task:** `docker history --no-trunc myimage`  
**Concept:** Understand image composition  

**Exercise 217: Squash Layers (Experimental)**  
**Goal:** Flatten layers  
**Task:** `docker build --squash -t myimage .`  
**Concept:** Combine all layers into one  
**Note:** Loses cache benefits

**Exercise 218: BuildKit Features** ⭐  
**Goal:** Modern build system  
**Task:** `DOCKER_BUILDKIT=1 docker build . `  
**Concept:** Faster, more features  
**Note:** Default in newer Docker versions

**Exercise 219: BuildKit Cache Mounts**  
**Goal:** Persistent build cache  
**Task:** `RUN --mount=type=cache,target=/root/.cache pip install -r requirements.txt`  
**Concept:** Speed up repeated builds  

**Exercise 220: BuildKit Secret Mounts** ⭐  
**Goal:** Safely use secrets in build  
**Task:** `RUN --mount=type=secret,id=mypassword cat /run/secrets/mypassword`  
**Concept:** Secrets not stored in layers  
**Security:** Much safer than ENV or COPY

---

## 🔄 PHASE 6: Docker Compose (Exercises 221-300)

### Week 23: Compose Basics

**Exercise 221: Install Docker Compose**  
**Goal:** Get Compose ready  
**Task:** Check `docker compose version`  
**Concept:** Compose is included with Docker Desktop  
**Note:** Modern Docker uses `docker compose` (space)

**Exercise 222: First compose. yaml** ⭐  
**Goal:** Create Compose file  
**Task:** Create `compose.yaml` with one service  
```yaml
services:
  web:
    image: nginx
```
**Concept:** Define services in YAML  

**Exercise 223: Start Compose**  
**Goal:** Launch services  
**Task:** `docker compose up`  
**Concept:** Starts all defined services  

**Exercise 224: Start in Background** ⭐  
**Goal:** Detached mode  
**Task:** `docker compose up -d`  
**Concept:** Run without blocking terminal  

**Exercise 225: View Compose Services**  
**Goal:** List running services  
**Task:** `docker compose ps`  
**Concept:** Shows containers from compose  

**Exercise 226: View Compose Logs**  
**Goal:** See all service logs  
**Task:** `docker compose logs`  
**Concept:** Combined logs from all services  

**Exercise 227: Follow Compose Logs**  
**Goal:** Stream logs  
**Task:** `docker compose logs -f`  
**Concept:** Watch logs in real-time  

**Exercise 228: Stop Compose** ⭐  
**Goal:** Stop all services  
**Task:** `docker compose stop`  
**Concept:** Stops but keeps containers  

**Exercise 229: Start Compose**  
**Goal:** Restart stopped services  
**Task:** `docker compose start`  
**Concept:** Start existing containers  

**Exercise 230: Down Compose** ⭐  
**Goal:** Stop and remove everything  
**Task:** `docker compose down`  
**Concept:** Removes containers, networks  

---

### Week 24: Compose Services

**Exercise 231: Multiple Services** ⭐  
**Goal:** Define two services  
**Task:** 
```yaml
services:
  web:
    image: nginx
  db:
    image: postgres
```
**Concept:** Multi-container applications  

**Exercise 232: Service with Ports** ⭐  
**Goal:** Expose ports  
**Task:** 
```yaml
services:
  web:
    image: nginx
    ports:
      - "8080:80"
```
**Concept:** Port mapping in Compose  

**Exercise 233: Multiple Ports**  
**Goal:** Expose several ports  
**Task:** Add multiple entries under `ports:`  
**Concept:** Same as multiple `-p` flags  

**Exercise 234: Service with Environment** ⭐  
**Goal:** Set environment variables  
**Task:** 
```yaml
services:
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: secret
```
**Concept:** Configure services via env  

**Exercise 235: Environment from List**  
**Goal:** Alternative syntax  
**Task:** 
```yaml
environment:
  - POSTGRES_PASSWORD=secret
```
**Concept:** List format for env vars  

**Exercise 236: Env File**  
**Goal:** External environment file  
**Task:** 
```yaml
services:
  app:
    image: myapp
    env_file:
      - .env
```
**Concept:** Keep secrets in . env file  

**Exercise 237: Service with Volumes** ⭐  
**Goal:** Persist data  
**Task:** 
```yaml
services:
  db:
    image: postgres
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```
**Concept:** Named volumes in Compose  

**Exercise 238: Bind Mount in Compose**  
**Goal:** Mount local directory  
**Task:** 
```yaml
volumes:
  - ./src:/app/src
```
**Concept:** Development workflow  

**Exercise 239: Read-Only Volume**  
**Goal:** Prevent writes  
**Task:** 
```yaml
volumes:
  - ./config:/etc/config:ro
```
**Concept:** Same as command line `:ro`  

**Exercise 240: Service Dependencies** ⭐  
**Goal:** Start order  
**Task:** 
```yaml
services:
  web:
    depends_on:
      - db
  db:
    image: postgres
```
**Concept:** db starts before web  

---

### Week 25: Compose Networking

**Exercise 241: Default Network**  
**Goal:** Understand automatic network  
**Task:** Start two services, they can reach each other  
**Concept:** Compose creates network automatically  

**Exercise 242: Service Name as Hostname** ⭐  
**Goal:** Service discovery  
**Task:** From web container, `ping db`  
**Concept:** Service names are DNS names  

**Exercise 243: Custom Network**  
**Goal:** Define explicit network  
**Task:** 
```yaml
services:
  web:
    networks:
      - frontend
networks:
  frontend:
```
**Concept:** Custom network configuration  

**Exercise 244: Multiple Networks**  
**Goal:** Isolate services  
**Task:** 
```yaml
services:
  web:
    networks:
      - frontend
  api:
    networks:
      - frontend
      - backend
  db:
    networks:
      - backend
```
**Concept:** web can't reach db directly  

**Exercise 245: Network Aliases**  
**Goal:** Alternative hostnames  
**Task:** 
```yaml
services:
  db:
    networks:
      backend:
        aliases:
          - database
          - mysql
```
**Concept:** Multiple names for service  

**Exercise 246: Connect to External Network**  
**Goal:** Use existing network  
**Task:** 
```yaml
networks:
  existing:
    external: true
    name: my-existing-network
```
**Concept:** Share network with other projects  

**Exercise 247: Expose vs Ports**  
**Goal:** Internal vs external  
**Task:** 
```yaml
expose:
  - "3306"
```
**Concept:** expose = container-to-container only  

**Exercise 248: Network Driver**  
**Goal:** Specify driver  
**Task:** 
```yaml
networks:
  mynet:
    driver: bridge
```
**Concept:** Usually bridge for single host  

**Exercise 249: Static IP Address**  
**Goal:** Fixed IP for service  
**Task:** 
```yaml
services:
  db:
    networks:
      mynet:
        ipv4_address: 172.20.0.5
networks:
  mynet:
    ipam:
      config:
        - subnet: 172.20. 0.0/16
```
**Concept:** Predictable IP addresses  

**Exercise 250: Network Mode Host** 📝  
**Goal:** Use host networking  
**Task:** 
```yaml
services:
  app:
    network_mode: host
```
**Concept:** No network isolation  

---

### Week 26: Compose Builds

**Exercise 251: Build in Compose** ⭐  
**Goal:** Build image from Dockerfile  
**Task:** 
```yaml
services:
  app:
    build: .
```
**Concept:** Build image during `compose up`  

**Exercise 252: Build Context**  
**Goal:** Specify build directory  
**Task:** 
```yaml
build:
  context: ./app
```
**Concept:** Where Dockerfile is located  

**Exercise 253: Custom Dockerfile**  
**Goal:** Use different Dockerfile name  
**Task:** 
```yaml
build:
  context: . 
  dockerfile: Dockerfile.dev
```
**Concept:** Multiple Dockerfiles in project  

**Exercise 254: Build Args in Compose**  
**Goal:** Pass build arguments  
**Task:** 
```yaml
build:
  context: . 
  args:
    VERSION: 2.0
```
**Concept:** Customize builds  

**Exercise 255: Named Build**  
**Goal:** Name the built image  
**Task:** 
```yaml
services:
  app:
    build: . 
    image: myapp:latest
```
**Concept:** Tag built image  

**Exercise 256: Build and Push**  
**Goal:** Build then push  
**Task:** `docker compose build` then `docker compose push`  
**Concept:** Separate build from run  

**Exercise 257: Force Rebuild**  
**Goal:** Ignore cache  
**Task:** `docker compose build --no-cache`  
**Concept:** Fresh build  

**Exercise 258: Pull Before Build**  
**Goal:** Update base images  
**Task:** `docker compose build --pull`  
**Concept:** Get latest base image  

**Exercise 259: Build Specific Service**  
**Goal:** Build one service  
**Task:** `docker compose build app`  
**Concept:** Target specific service  

**Exercise 260: Watch Mode** 📝 ⭐  
**Goal:** Auto-rebuild on changes  
**Task:** `docker compose watch`  
**Concept:** Development workflow  
**Note:** Requires compose v2.22+

---

### Week 27: Compose Commands

**Exercise 261: Run One-off Command**  
**Goal:** Execute command in service  
**Task:** `docker compose run web bash`  
**Concept:** Creates new container for command  

**Exercise 262: Exec in Running Service** ⭐  
**Goal:** Command in existing container  
**Task:** `docker compose exec db psql -U postgres`  
**Concept:** Uses running container  

**Exercise 263: Scale Services** ⭐  
**Goal:** Multiple instances  
**Task:** `docker compose up -d --scale web=3`  
**Concept:** Run multiple copies  
**Note:** Can't use specific host ports

**Exercise 264: Stop Specific Service**  
**Goal:** Stop one service  
**Task:** `docker compose stop web`  
**Concept:** Other services keep running  

**Exercise 265: Restart Specific Service**  
**Goal:** Restart one service  
**Task:** `docker compose restart api`  
**Concept:** Don't affect others  

**Exercise 266: View Service Config**  
**Goal:** Debug configuration  
**Task:** `docker compose config`  
**Concept:** Shows resolved configuration  

**Exercise 267: Validate Compose File**  
**Goal:** Check for errors  
**Task:** `docker compose config --quiet`  
**Concept:** Returns error if invalid  

**Exercise 268: Pull Images** ⭐  
**Goal:** Download all images  
**Task:** `docker compose pull`  
**Concept:** Update to latest  

**Exercise 269: Down with Volumes**  
**Goal:** Remove volumes too  
**Task:** `docker compose down -v`  
**Concept:** Clean up everything  
**Warning:** Deletes data!

**Exercise 270: Down with Images**  
**Goal:** Remove images too  
**Task:** `docker compose down --rmi all`  
**Concept:** Complete cleanup  

---

### Week 28: Advanced Compose

**Exercise 271: Healthcheck in Compose** ⭐  
**Goal:** Configure health checks  
**Task:** 
```yaml
services:
  web:
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/"]
      interval: 30s
      timeout: 10s
      retries: 3
```
**Concept:** Monitor service health  

**Exercise 272: depends_on with Condition** ⭐  
**Goal:** Wait for healthy  
**Task:** 
```yaml
depends_on:
  db:
    condition: service_healthy
```
**Concept:** Start after dependency healthy  

**Exercise 273: Restart Policy**  
**Goal:** Auto-restart containers  
**Task:** 
```yaml
services:
  web:
    restart: always
```
**Concept:** Restart on failure or reboot  
**Options:** no, always, on-failure, unless-stopped

**Exercise 274: Resource Limits** ⭐  
**Goal:** Limit CPU and memory  
**Task:** 
```yaml
services:
  app:
    deploy:
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
```
**Concept:** Prevent resource hogging  

**Exercise 275: Logging Configuration**  
**Goal:** Configure log driver  
**Task:** 
```yaml
services:
  app:
    logging:
      driver: json-file
      options:
        max-size: "10m"
        max-file: "3"
```
**Concept:** Prevent disk fill from logs  

**Exercise 276: Command Override**  
**Goal:** Override default command  
**Task:** 
```yaml
services:
  app:
    command: python manage.py runserver
```
**Concept:** Different command than Dockerfile  

**Exercise 277: Entrypoint Override**  
**Goal:** Override entrypoint  
**Task:** 
```yaml
services:
  app:
    entrypoint: /custom-entrypoint.sh
```
**Concept:** Change startup behavior  

**Exercise 278: Working Directory**  
**Goal:** Set working dir  
**Task:** 
```yaml
services:
  app:
    working_dir: /app/src
```
**Concept:** Where commands run  

**Exercise 279: User Override**  
**Goal:** Run as specific user  
**Task:** 
```yaml
services:
  app:
    user: "1000:1000"
```
**Concept:** Non-root execution  

**Exercise 280: Privileged Mode**  
**Goal:** Full host access  
**Task:** 
```yaml
services:
  app:
    privileged: true
```
**Concept:** Needed for some system tasks  
**Warning:** Security risk!

---

### Week 29: Compose Profiles & Extensions

**Exercise 281: Compose Profiles** ⭐  
**Goal:** Optional services  
**Task:** 
```yaml
services:
  web:
    image: nginx
  debug:
    image: busybox
    profiles:
      - debug
```
**Concept:** `docker compose --profile debug up`  

**Exercise 282: Multiple Profiles**  
**Goal:** Service in multiple profiles  
**Task:** 
```yaml
profiles:
  - dev
  - debug
```
**Concept:** Activate with any matching profile  

**Exercise 283: Extension Fields** ⭐  
**Goal:** Reusable configuration  
**Task:** 
```yaml
x-common: &common
  restart: always
  logging:
    driver: json-file

services:
  web:
    <<: *common
    image: nginx
```
**Concept:** DRY principle in Compose  

**Exercise 284: Multiple Compose Files**  
**Goal:** Override configurations  
**Task:** `docker compose -f compose.yaml -f compose. override.yaml up`  
**Concept:** Layer configurations  

**Exercise 285: Development Override**  
**Goal:** Dev-specific settings  
**Task:** Create `compose.override.yaml` with dev settings  
**Concept:** Auto-loaded if exists  

**Exercise 286: Production Override**  
**Goal:** Prod-specific settings  
**Task:** Create `compose.prod.yaml`  
**Concept:** Explicit `-f` required  

**Exercise 287: Include Other Files**  
**Goal:** Modular compose  
**Task:** 
```yaml
include:
  - ./db/compose.yaml
  - ./cache/compose.yaml
```
**Concept:** Split large configurations  

**Exercise 288: Variable Substitution** ⭐  
**Goal:** Use environment in compose  
**Task:** 
```yaml
services:
  web:
    image: nginx:${NGINX_VERSION:-latest}
```
**Concept:** Dynamic configuration  

**Exercise 289: . env File for Compose**  
**Goal:** Default variables  
**Task:** Create `.env` with `NGINX_VERSION=1.25`  
**Concept:** Auto-loaded for substitution  

**Exercise 290: Interpolation Defaults**  
**Goal:** Fallback values  
**Task:** `${VAR:-default}` syntax  
**Concept:** Use default if not set  

---

### Week 30: Real-World Compose Projects

**Exercise 291: WordPress + MySQL** 📝 ⭐  
**Goal:** Complete CMS setup  
**Task:** 
```yaml
services:
  wordpress:
    image: wordpress
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_PASSWORD: secret
    volumes:
      - wp-content:/var/www/html/wp-content
    depends_on:
      - db
  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: wordpress
    volumes:
      - db-data:/var/lib/mysql

volumes:
  wp-content:
  db-data:
```
**Concept:** Multi-container application  

**Exercise 292: LAMP Stack**  
**Goal:** Linux, Apache, MySQL, PHP  
**Task:** Create compose with php-apache + mysql  
**Concept:** Classic web stack  

**Exercise 293: MEAN Stack**  
**Goal:** MongoDB, Express, Angular, Node  
**Task:** Create compose for MEAN  
**Concept:** JavaScript full stack  

**Exercise 294: Django + PostgreSQL** 📝  
**Goal:** Python web framework  
**Task:** Django app with Postgres  
**Concept:** Python stack  

**Exercise 295: Rails + PostgreSQL**  
**Goal:** Ruby web framework  
**Task:** Rails app with Postgres  
**Concept:** Ruby stack  

**Exercise 296: Laravel + MySQL**  
**Goal:** PHP framework  
**Task:** Laravel with MySQL  
**Concept:** PHP stack  

**Exercise 297: Nginx Reverse Proxy** ⭐  
**Goal:** Load balancer setup  
**Task:** Nginx in front of multiple app containers  
**Concept:** Production pattern  

**Exercise 298: Redis Cache**  
**Goal:** Add caching layer  
**Task:** Add Redis to existing app  
**Concept:** Performance optimization  

**Exercise 299: Monitoring Stack**  
**Goal:** Observe your containers  
**Task:** Add Prometheus + Grafana  
**Concept:** Observability  

**Exercise 300: Full Production Stack** 📝 ⭐  
**Goal:** Complete application  
**Task:** App + DB + Cache + Proxy + Monitoring  
**Concept:** Real-world architecture  

---

## 🔐 PHASE 7: Security & Best Practices (Exercises 301-350)

### Week 31: Container Security Basics

**Exercise 301: Don't Run as Root** ⭐  
**Goal:** Non-root containers  
**Task:** Add `USER` instruction to Dockerfile  
**Concept:** Limit container privileges  

**Exercise 302: Check Running User**  
**Goal:** Verify non-root  
**Task:** `docker exec <id> whoami`  
**Concept:** Confirm security setting  

**Exercise 303: Read-Only Filesystem** ⭐  
**Goal:** Immutable containers  
**Task:** `docker run --read-only nginx`  
**Concept:** Prevent runtime modifications  

**Exercise 304: Drop Capabilities**  
**Goal:** Reduce permissions  
**Task:** `docker run --cap-drop ALL --cap-add NET_BIND_SERVICE nginx`  
**Concept:** Principle of least privilege  

**Exercise 305: List Default Capabilities**  
**Goal:** Understand defaults  
**Task:** Research Docker default capabilities  
**Concept:** Containers have limited caps by default  

**Exercise 306: No New Privileges**  
**Goal:** Prevent privilege escalation  
**Task:** `docker run --security-opt no-new-privileges nginx`  
**Concept:** Blocks setuid/setgid  

**Exercise 307: Seccomp Profiles**  
**Goal:** Syscall filtering  
**Task:** `docker run --security-opt seccomp=default. json nginx`  
**Concept:** Limit system calls  

**Exercise 308: AppArmor/SELinux**  
**Goal:** Mandatory access control  
**Task:** Check if enabled on your system  
**Concept:** Additional security layers  

**Exercise 309: Scan Image for Vulnerabilities** ⭐  
**Goal:** Find security issues  
**Task:** `docker scout cves nginx`  
**Concept:** Identify known vulnerabilities  
**Alternative:** Trivy, Snyk, Grype

**Exercise 310: Update Base Images** ⭐  
**Goal:** Patch vulnerabilities  
**Task:** Pull latest and rebuild  
**Concept:** Regular updates essential  

---

### Week 32: Secrets Management

**Exercise 311: Don't Use ENV for Secrets** ⭐  
**Goal:** Understand the risk  
**Task:** `docker inspect` shows all ENV vars  
**Concept:** ENV is visible, not secure  

**Exercise 312: Docker Secrets Intro**  
**Goal:** Understand secrets feature  
**Task:** Create secret: `echo "password" | docker secret create my_secret -`  
**Concept:** Secure secret storage  
**Note:** Requires Swarm mode for full features

**Exercise 313: Mount Secrets in Container**  
**Goal:** Use secrets  
**Task:** Secret appears as file in `/run/secrets/`  
**Concept:** Read secret from file  

**Exercise 314: Compose Secrets** ⭐  
**Goal:** Secrets in Compose  
**Task:** 
```yaml
services:
  db:
    secrets:
      - db_password
secrets:
  db_password:
    file: ./secrets/db_password. txt
```
**Concept:** File-based secrets  

**Exercise 315: External Secrets**  
**Goal:** Pre-created secrets  
**Task:** 
```yaml
secrets:
  api_key:
    external: true
```
**Concept:** Reference existing secrets  

**Exercise 316: Build-time Secrets** ⭐  
**Goal:** Secrets during build  
**Task:** `RUN --mount=type=secret,id=npmrc cat /run/secrets/npmrc`  
**Concept:** Not stored in image layers  

**Exercise 317: . env File Security**  
**Goal:** Protect env files  
**Task:** Add `.env` to `. gitignore`  
**Concept:** Never commit secrets  

**Exercise 318: Secret Rotation**  
**Goal:** Change secrets safely  
**Task:** Update secret, restart containers  
**Concept:** Regular rotation  

**Exercise 319: Environment vs Secret Decision**  
**Goal:** Know when to use each  
**Task:** ENV for config, secrets for sensitive data  
**Concept:** Right tool for job  

**Exercise 320: Vault Integration Preview**  
**Goal:** External secret management  
**Task:** Read about HashiCorp Vault  
**Concept:** Enterprise secret management  

---

### Week 33: Image Security

**Exercise 321: Use Official Images** ⭐  
**Goal:** Trusted base images  
**Task:** Use `nginx` not `randomuser/nginx`  
**Concept:** Official images are verified  

**Exercise 322: Verify Image Publisher**  
**Goal:** Check image source  
**Task:** Look for "Docker Official Image" badge  
**Concept:** Trust chain  

**Exercise 323: Pin Image Digests** ⭐  
**Goal:** Immutable image reference  
**Task:** `FROM nginx@sha256:abc123... `  
**Concept:** Tags can change, digests don't  

**Exercise 324: Get Image Digest**  
**Goal:** Find digest value  
**Task:** `docker images --digests nginx`  
**Concept:** SHA256 hash of image  

**Exercise 325: Minimize Attack Surface**  
**Goal:** Smaller = safer  
**Task:** Use slim/alpine/distroless  
**Concept:** Fewer packages, fewer vulnerabilities  

**Exercise 326: No Package Manager in Prod**  
**Goal:** Can't install malware  
**Task:** Remove apt/apk in final stage  
**Concept:** Defense in depth  

**Exercise 327: Sign Images**  
**Goal:** Verify image integrity  
**Task:** `docker trust sign myimage:latest`  
**Concept:** Content trust / Notary  

**Exercise 328: Enable Content Trust**  
**Goal:** Only run signed images  
**Task:** `export DOCKER_CONTENT_TRUST=1`  
**Concept:** Refuse unsigned images  

**Exercise 329: Scan in CI/CD**  
**Goal:** Automate security checks  
**Task:** Add scanning to build pipeline  
**Concept:** Shift left security  

**Exercise 330: Image Allowlisting**  
**Goal:** Control which images allowed  
**Task:** Configure registry restrictions  
**Concept:** Enterprise security  

---

### Week 34: Network Security

**Exercise 331: Internal Networks** ⭐  
**Goal:** No external access  
**Task:** `docker network create --internal secure`  
**Concept:** Containers can't reach internet  

**Exercise 332: Network Segmentation**  
**Goal:** Isolate services  
**Task:** Different networks for different tiers  
**Concept:** Limit blast radius  

**Exercise 333: Limit Published Ports**  
**Goal:** Minimal exposure  
**Task:** Only publish necessary ports  
**Concept:** Reduce attack surface  

**Exercise 334: Bind to Localhost**  
**Goal:** Local-only access  
**Task:** `-p 127.0. 0.1:8080:80`  
**Concept:** Not accessible from network  

**Exercise 335: Use TLS**  
**Goal:** Encrypt traffic  
**Task:** Configure HTTPS in containers  
**Concept:** Encrypt in transit  

**Exercise 336: Network Policies**  
**Goal:** Firewall rules  
**Task:** Use iptables or network plugins  
**Concept:** Control traffic flow  

**Exercise 337: Disable ICC**  
**Goal:** No inter-container comm  
**Task:** `--icc=false` on daemon  
**Concept:** Containers can't talk by default  

**Exercise 338: Use Aliases Not IPs**  
**Goal:** Don't hardcode IPs  
**Task:** Always use service names  
**Concept:** IPs change, names don't  

**Exercise 339: DNS Security**  
**Goal:** Secure name resolution  
**Task:** Use Docker's internal DNS  
**Concept:** Avoid DNS spoofing  

**Exercise 340: Audit Network Connections**  
**Goal:** Monitor traffic  
**Task:** Check `netstat` inside containers  
**Concept:** Know what's communicating  

---

### Week 35: Runtime Security

**Exercise 341: Resource Limits** ⭐  
**Goal:** Prevent DoS  
**Task:** `--memory=512m --cpus=0. 5`  
**Concept:** Limit resource consumption  

**Exercise 342: PID Limits**  
**Goal:** Prevent fork bombs  
**Task:** `--pids-limit=100`  
**Concept:** Limit process count  

**Exercise 343: Ulimits**  
**Goal:** Set resource limits  
**Task:** `--ulimit nofile=1024:1024`  
**Concept:** Linux resource limits  

**Exercise 344: No Privileged Containers** ⭐  
**Goal:** Never use privileged  
**Task:** Avoid `--privileged` flag  
**Concept:** Full host access is dangerous  

**Exercise 345: Specific Capabilities Only**  
**Goal:** Add only what's needed  
**Task:** `--cap-drop ALL --cap-add <specific>`  
**Concept:** Minimal capabilities  

**Exercise 346: No Host Namespaces**  
**Goal:** Maintain isolation  
**Task:** Avoid `--pid=host`, `--network=host`  
**Concept:** Keep namespaces separate  

**Exercise 347: Protect Docker Socket** ⭐  
**Goal:** Secure daemon access  
**Task:** Never mount `/var/run/docker.sock` in production  
**Concept:** Socket = root access  

**Exercise 348: Use Read-Only Bind Mounts**  
**Goal:** Limit mount permissions  
**Task:** Always use `:ro` when possible  
**Concept:** Prevent unwanted writes  

**Exercise 349: Logging and Auditing**  
**Goal:** Track container activity  
**Task:** Configure logging driver  
**Concept:** Forensics and compliance  

**Exercise 350: Security Checklist** 📝 ⭐  
**Goal:** Review all security practices  
**Task:** Create checklist for your projects  
**Concept:** Systematic security approach  

---

## ⚙️ PHASE 8: Docker Engine & Daemon (Exercises 351-400)

### Week 36: Docker Daemon Configuration

**Exercise 351: Find Docker Config**  
**Goal:** Locate daemon config  
**Task:** Check `/etc/docker/daemon.json`  
**Concept:** Daemon configuration file  

**Exercise 352: View Current Config**  
**Goal:** See active settings  
**Task:** `docker system info`  
**Concept:** Current daemon configuration  

**Exercise 353: Change Storage Driver**  
**Goal:** Configure storage  
**Task:** Add `"storage-driver": "overlay2"` to daemon. json  
**Concept:** How images/containers stored  

**Exercise 354: Set Default Logging**  
**Goal:** Configure log driver  
**Task:** 
```json
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  }
}
```
**Concept:** Default for all containers  

**Exercise 355: Restart Docker Daemon**  
**Goal:** Apply config changes  
**Task:** `sudo systemctl restart docker`  
**Concept:** Config loaded at startup  

**Exercise 356: Live Reload Config**  
**Goal:** Reload without restart  
**Task:** `sudo kill -SIGHUP $(pidof dockerd)`  
**Concept:** Some settings reload live  

**Exercise 357: Set Data Root**  
**Goal:** Change storage location  
**Task:** `"data-root": "/mnt/docker"`  
**Concept:** Move Docker data directory  

**Exercise 358: Configure DNS**  
**Goal:** Default DNS servers  
**Task:** `"dns": ["8.8.8.8", "8.8.4. 4"]`  
**Concept:** Inherited by containers  

**Exercise 359: Configure Registry Mirrors**  
**Goal:** Speed up pulls  
**Task:** `"registry-mirrors": ["https://mirror. example.com"]`  
**Concept:** Cache registry locally  

**Exercise 360: Insecure Registries**  
**Goal:** Allow HTTP registries  
**Task:** `"insecure-registries": ["localhost:5000"]`  
**Concept:** Development only!   
**Warning:** Not for production

---

### Week 37: Docker Storage

**Exercise 361: Check Storage Driver**  
**Goal:** See current driver  
**Task:** `docker info | grep "Storage Driver"`  
**Concept:** overlay2 is recommended  

**Exercise 362: View Disk Usage** ⭐  
**Goal:** Check Docker disk use  
**Task:** `docker system df`  
**Concept:** Images, containers, volumes, cache  

**Exercise 363: Detailed Disk Usage**  
**Goal:** Verbose disk info  
**Task:** `docker system df -v`  
**Concept:** Per-item breakdown  

**Exercise 364: Prune Everything** ⭐  
**Goal:** Reclaim disk space  
**Task:** `docker system prune -a`  
**Concept:** Remove all unused data  
**Warning:** Deletes stopped containers, unused images! 

**Exercise 365: Prune with Volumes**  
**Goal:** Include volumes  
**Task:** `docker system prune -a --volumes`  
**Concept:** Complete cleanup  
**Warning:** Deletes data! 

**Exercise 366: Prune by Age**  
**Goal:** Remove old items  
**Task:** `docker image prune -a --filter "until=24h"`  
**Concept:** Keep recent items  

**Exercise 367: Image Layer Sharing**  
**Goal:** Understand layers  
**Task:** Pull two images with same base  
**Concept:** Shared layers save space  

**Exercise 368: Check Layer Contents**  
**Goal:** See layer details  
**Task:** `docker history <image>`  
**Concept:** Each layer has size  

**Exercise 369: Build Cache**  
**Goal:** Understand build cache  
**Task:** Build same Dockerfile twice  
**Concept:** Cached layers are fast  

**Exercise 370: Clear Build Cache**  
**Goal:** Remove cache  
**Task:** `docker builder prune`  
**Concept:** Free disk space  

---

### Week 38: Docker Contexts & Remote

**Exercise 371: List Contexts**  
**Goal:** See available contexts  
**Task:** `docker context ls`  
**Concept:** Manage multiple Docker hosts  

**Exercise 372: Current Context**  
**Goal:** Check active context  
**Task:** `docker context show`  
**Concept:** Which Docker you're controlling  

**Exercise 373: Create Context**  
**Goal:** Add remote Docker  
**Task:** `docker context create remote --docker "host=ssh://user@remote"`  
**Concept:** SSH to remote Docker  

**Exercise 374: Switch Context** ⭐  
**Goal:** Use different Docker  
**Task:** `docker context use remote`  
**Concept:** Commands go to remote  

**Exercise 375: One-time Context**  
**Goal:** Use context once  
**Task:** `docker --context remote ps`  
**Concept:** Don't change default  

**Exercise 376: Remove Context**  
**Goal:** Delete context  
**Task:** `docker context rm remote`  
**Concept:** Cleanup unused  

**Exercise 377: Export Context**  
**Goal:** Share context  
**Task:** `docker context export remote > remote.dockercontext`  
**Concept:** Transfer to another machine  

**Exercise 378: Import Context**  
**Goal:** Add exported context  
**Task:** `docker context import remote remote.dockercontext`  
**Concept:** Load shared context  

**Exercise 379: Docker over SSH** ⭐  
**Goal:** Control remote Docker  
**Task:** `docker -H ssh://user@host ps`  
**Concept:** No context needed  

**Exercise 380: Docker TCP Socket**  
**Goal:** Expose daemon on network  
**Task:** Configure `"hosts": ["tcp://0.0.0. 0:2375"]`  
**Concept:** Remote access  
**Warning:** Very insecure without TLS!

---

### Week 39: Logging & Monitoring

**Exercise 381: View Container Logs** ⭐  
**Goal:** See container output  
**Task:** `docker logs <container>`  
**Concept:** stdout/stderr captured  

**Exercise 382: Follow Logs**  
**Goal:** Stream logs  
**Task:** `docker logs -f <container>`  
**Concept:** Real-time log viewing  

**Exercise 383: Tail Logs**  
**Goal:** Recent logs only  
**Task:** `docker logs --tail 100 <container>`  
**Concept:** Last N lines  

**Exercise 384: Timestamps in Logs**  
**Goal:** See when events happened  
**Task:** `docker logs -t <container>`  
**Concept:** Add timestamps  

**Exercise 385: Logs Since Time**  
**Goal:** Filter by time  
**Task:** `docker logs --since 1h <container>`  
**Concept:** Recent logs only  

**Exercise 386: syslog Driver**  
**Goal:** Send to syslog  
**Task:** `docker run --log-driver syslog nginx`  
**Concept:** Centralized logging  

**Exercise 387: journald Driver**  
**Goal:** Send to journald  
**Task:** `docker run --log-driver journald nginx`  
**Concept:** systemd integration  

**Exercise 388: Container Events** ⭐  
**Goal:** Watch Docker events  
**Task:** `docker events`  
**Concept:** Start, stop, die events  

**Exercise 389: Filter Events**  
**Goal:** Specific events only  
**Task:** `docker events --filter type=container`  
**Concept:** Reduce noise  

**Exercise 390: Container Stats** ⭐  
**Goal:** Live resource usage  
**Task:** `docker stats`  
**Concept:** CPU, memory, network, I/O  

---

### Week 40: Docker Plugins & Extensions

**Exercise 391: List Plugins**  
**Goal:** See installed plugins  
**Task:** `docker plugin ls`  
**Concept:** Extend Docker functionality  

**Exercise 392: Install Plugin**  
**Goal:** Add new plugin  
**Task:** `docker plugin install vieux/sshfs`  
**Concept:** Volume, network, auth plugins  

**Exercise 393: Enable/Disable Plugin**  
**Goal:** Control plugin state  
**Task:** `docker plugin disable <plugin>`  
**Concept:** Turn off without removing  

**Exercise 394: Plugin Configuration**  
**Goal:** Configure plugin  
**Task:** `docker plugin set <plugin> <key>=<value>`  
**Concept:** Customize plugin behavior  

**Exercise 395: Remove Plugin**  
**Goal:** Uninstall plugin  
**Task:** `docker plugin rm <plugin>`  
**Concept:** Clean up unused  

**Exercise 396: Volume Plugin**  
**Goal:** Use storage plugin  
**Task:** Create volume with plugin driver  
**Concept:** External storage backends  

**Exercise 397: Network Plugin**  
**Goal:** Custom networking  
**Task:** Install network driver plugin  
**Concept:** Advanced networking  

**Exercise 398: Docker Desktop Extensions**  
**Goal:** GUI extensions  
**Task:** Browse extensions in Docker Desktop  
**Concept:** Extend Desktop functionality  

**Exercise 399: Build Extensions**  
**Goal:** Custom extensions  
**Task:** Read extension documentation  
**Concept:** Create your own tools  

**Exercise 400: Plugin Security** 📝  
**Goal:** Understand plugin risks  
**Task:** Review plugin permissions  
**Concept:** Plugins have broad access  

---

## 🏭 PHASE 9: CI/CD & Automation (Exercises 401-450)

### Week 41: Building Images Automatically

**Exercise 401: Docker in CI/CD** ⭐  
**Goal:** Understand the workflow  
**Task:** Draw build → test → push → deploy flow  
**Concept:** Automated image lifecycle  

**Exercise 402: Build Script**  
**Goal:** Reproducible builds  
**Task:** Create `build.sh` with docker build command  
**Concept:** Scripted builds  

**Exercise 403: Tag with Git SHA** ⭐  
**Goal:** Traceable images  
**Task:** `docker build -t myapp:$(git rev-parse --short HEAD) .`  
**Concept:** Connect image to code  

**Exercise 404: Tag with Version**  
**Goal:** Semantic versioning  
**Task:** `docker build -t myapp:1.2.3 .`  
**Concept:** Version tracking  

**Exercise 405: Multiple Tags**  
**Goal:** Tag same image multiple ways  
**Task:** `docker tag myapp:abc123 myapp:latest`  
**Concept:** One image, many names  

**Exercise 406: Build Matrix**  
**Goal:** Multiple platform builds  
**Task:** Build for different architectures  
**Concept:** Cross-platform images  

**Exercise 407: Buildx for Multi-platform** ⭐  
**Goal:** ARM and AMD64  
**Task:** `docker buildx build --platform linux/amd64,linux/arm64 .`  
**Concept:** Single command, multiple archs  

**Exercise 408: Setup Buildx**  
**Goal:** Configure buildx  
**Task:** `docker buildx create --use`  
**Concept:** Multi-platform builder  

**Exercise 409: Push Multi-platform**  
**Goal:** Push manifest list  
**Task:** `docker buildx build --platform linux/amd64,linux/arm64 --push .`  
**Concept:** Registry picks right arch  

**Exercise 410: Build Cache in CI**  
**Goal:** Speed up CI builds  
**Task:** Use `--cache-from` and `--cache-to`  
**Concept:** Cache across builds  

---

### Week 42: Testing Containers

**Exercise 411: Test Container Starts**  
**Goal:** Basic smoke test  
**Task:** Run container, check exit code  
**Concept:** Verify image works  

**Exercise 412: Test HTTP Response**  
**Goal:** Application responds  
**Task:** `curl -f http://localhost:port/health`  
**Concept:** Health check test  

**Exercise 413: Container Structure Tests**  
**Goal:** Test image contents  
**Task:** Use container-structure-test tool  
**Concept:** Verify files, commands exist  

**Exercise 414: Run Tests in Container** ⭐  
**Goal:** Execute test suite  
**Task:** `docker run myapp npm test`  
**Concept:** Consistent test environment  

**Exercise 415: Test with Compose**  
**Goal:** Integration tests  
**Task:** Compose with app + db, run tests  
**Concept:** Full stack testing  

**Exercise 416: Test Healthcheck**  
**Goal:** Verify healthcheck works  
**Task:** Check container health status  
**Concept:** Health monitoring  

**Exercise 417: Lint Dockerfile** ⭐  
**Goal:** Dockerfile best practices  
**Task:** Use hadolint  
**Concept:** Static analysis  

**Exercise 418: Security Scan in CI**  
**Goal:** Automated vulnerability scan  
**Task:** Add Trivy/Snyk to pipeline  
**Concept:** Security gates  

**Exercise 419: Test Compose Config**  
**Goal:** Validate compose file  
**Task:** `docker compose config` in CI  
**Concept:** Catch config errors  

**Exercise 420: End-to-end Tests**  
**Goal:** Full application test  
**Task:** Browser tests against containers  
**Concept:** Real user simulation  

---

### Week 43: Local Registry

**Exercise 421: Run Local Registry** ⭐  
**Goal:** Your own registry  
**Task:** `docker run -d -p 5000:5000 registry:2`  
**Concept:** Store images locally  

**Exercise 422: Push to Local Registry** ⭐  
**Goal:** Upload image  
**Task:** 
```bash
docker tag myapp localhost:5000/myapp
docker push localhost:5000/myapp
```
**Concept:** Push to any registry  

**Exercise 423: Pull from Local Registry**  
**Goal:** Download image  
**Task:** `docker pull localhost:5000/myapp`  
**Concept:** Distribute images locally  

**Exercise 424: List Registry Contents**  
**Goal:** See stored images  
**Task:** `curl http://localhost:5000/v2/_catalog`  
**Concept:** Registry API  

**Exercise 425: List Image Tags**  
**Goal:** See available versions  
**Task:** `curl http://localhost:5000/v2/myapp/tags/list`  
**Concept:** Query registry  

**Exercise 426: Registry with Volume**  
**Goal:** Persist registry data  
**Task:** Add volume to registry container  
**Concept:** Survive restarts  

**Exercise 427: Registry with TLS**  
**Goal:** Secure registry  
**Task:** Configure certs for registry  
**Concept:** HTTPS registry  

**Exercise 428: Registry Authentication**  
**Goal:** Protected registry  
**Task:** Add htpasswd authentication  
**Concept:** Control access  

**Exercise 429: Registry Garbage Collection**  
**Goal:** Clean up old images  
**Task:** `registry garbage-collect`  
**Concept:** Reclaim storage  

**Exercise 430: Mirror Public Registry**  
**Goal:** Cache public images  
**Task:** Configure pull-through cache  
**Concept:** Faster pulls, offline access  

---

### Week 44: Deployment Automation

**Exercise 431: Deploy Script**  
**Goal:** Automated deployment  
**Task:** Script that pulls and runs new image  
**Concept:** Basic deployment automation  

**Exercise 432: Rolling Update Pattern**  
**Goal:** Zero-downtime deploy  
**Task:** Start new, wait healthy, stop old  
**Concept:** Continuous availability  

**Exercise 433: Blue-Green Deploy**  
**Goal:** Instant switchover  
**Task:** Run both versions, switch traffic  
**Concept:** Easy rollback  

**Exercise 434: Canary Deploy**  
**Goal:** Gradual rollout  
**Task:** Route small % to new version  
**Concept:** Reduce risk  

**Exercise 435: Rollback Procedure**  
**Goal:** Quick recovery  
**Task:** Keep previous image, switch back  
**Concept:** Fast recovery  

**Exercise 436: Environment Promotion**  
**Goal:** Dev → Staging → Prod  
**Task:** Same image, different config  
**Concept:** Environment parity  

**Exercise 437: Feature Flags**  
**Goal:** Toggle features  
**Task:** Use env vars for features  
**Concept:** Decouple deploy from release  

**Exercise 438: Deployment Hooks**  
**Goal:** Pre/post actions  
**Task:** Run migrations before deploy  
**Concept:** Lifecycle automation  

**Exercise 439: Health Check Gates**  
**Goal:** Only deploy if healthy  
**Task:** Check health before completing deploy  
**Concept:** Prevent bad deploys  

**Exercise 440: Deployment Notifications**  
**Goal:** Alert on deploy  
**Task:** Send message on deploy  
**Concept:** Team awareness  

---

### Week 45: Backup & Recovery

**Exercise 441: Backup Strategy** ⭐  
**Goal:** Plan data protection  
**Task:** Identify what needs backup  
**Concept:** Volumes, configs, images  

**Exercise 442: Volume Backup Script**  
**Goal:** Automated volume backup  
**Task:** Script using `docker run` to tar volume  
**Concept:** Consistent backups  

**Exercise 443: Scheduled Backups**  
**Goal:** Regular backups  
**Task:** Cron job for backups  
**Concept:** Automated schedule  

**Exercise 444: Backup Verification**  
**Goal:** Test backups work  
**Task:** Restore and verify  
**Concept:** Untested backup = no backup  

**Exercise 445: Image Backup**  
**Goal:** Save images  
**Task:** `docker save` important images  
**Concept:** Offline image storage  

**Exercise 446: Configuration Backup**  
**Goal:** Save Docker config  
**Task:** Backup daemon. json, compose files  
**Concept:** Infrastructure as code  

**Exercise 447: Disaster Recovery Plan**  
**Goal:** Complete recovery procedure  
**Task:** Document full recovery steps  
**Concept:** Know how to rebuild  

**Exercise 448: Recovery Time Testing**  
**Goal:** Measure recovery speed  
**Task:** Practice full restore  
**Concept:** RTO/RPO metrics  

**Exercise 449: Offsite Backups**  
**Goal:** Geographic redundancy  
**Task:** Copy backups to different location  
**Concept:** Survive site failure  

**Exercise 450: Backup Retention** 📝  
**Goal:** Manage backup lifecycle  
**Task:** Delete old backups automatically  
**Concept:** Storage management  

---

## 🔧 PHASE 10: Troubleshooting & Debugging (Exercises 451-500)

### Week 46: Container Debugging

**Exercise 451: Container Won't Start** ⭐  
**Goal:** Debug startup failure  
**Task:** Check `docker logs <container>`  
**Concept:** First place to look  

**Exercise 452: Check Exit Code**  
**Goal:** Understand failure  
**Task:** `docker inspect <container> | grep ExitCode`  
**Concept:** Exit code indicates problem  

**Exercise 453: Interactive Debug**  
**Goal:** Shell into failing container  
**Task:** Override entrypoint with shell  
**Concept:** Manual investigation  

**Exercise 454: Debug with Sidecar**  
**Goal:** Add debug tools  
**Task:** Run debug container with shared namespace  
**Concept:** Add tools without modifying image  

**Exercise 455: Exec into Running Container**  
**Goal:** Live debugging  
**Task:** `docker exec -it <container> sh`  
**Concept:** Access running process  

**Exercise 456: Check Process List**  
**Goal:** See what's running  
**Task:** `docker top <container>`  
**Concept:** Identify processes  

**Exercise 457: Check Resource Usage**  
**Goal:** Memory/CPU issues  
**Task:** `docker stats <container>`  
**Concept:** Resource bottlenecks  

**Exercise 458: OOM Killer Detection**  
**Goal:** Find memory kills  
**Task:** Check `docker inspect` for OOMKilled  
**Concept:** Out of memory deaths  

**Exercise 459: File System Investigation**  
**Goal:** Check container files  
**Task:** `docker exec` + `ls`, `cat`, `find`  
**Concept:** Verify expected files  

**Exercise 460: Environment Verification**  
**Goal:** Check environment  
**Task:** `docker exec <container> env`  
**Concept:** Confirm configuration  

---

### Week 47: Network Debugging

**Exercise 461: Container Can't Reach Internet** ⭐  
**Goal:** Debug connectivity  
**Task:** `docker exec <id> ping 8.8.8.8`  
**Concept:** Test external connectivity  

**Exercise 462: Container Can't Reach Container**  
**Goal:** Debug inter-container  
**Task:** Check they're on same network  
**Concept:** Network isolation  

**Exercise 463: DNS Resolution Failure**  
**Goal:** Debug DNS  
**Task:** `docker exec <id> nslookup <service>`  
**Concept:** Name resolution issues  

**Exercise 464: Check Container IP**  
**Goal:** Find IP address  
**Task:** `docker inspect -f '{{.NetworkSettings.IPAddress}}' <id>`  
**Concept:** Verify network config  

**Exercise 465: Port Not Accessible**  
**Goal:** Debug port publishing  
**Task:** `docker port <container>`  
**Concept:** Verify port mapping  

**Exercise 466: Check Listening Ports**  
**Goal:** App listening correctly  
**Task:** `docker exec <id> netstat -tlnp`  
**Concept:** Confirm app binding  

**Exercise 467: Network Inspection**  
**Goal:** Debug network config  
**Task:** `docker network inspect <network>`  
**Concept:** See connected containers  

**Exercise 468: tcpdump in Container**  
**Goal:** Capture packets  
**Task:** Install and run tcpdump  
**Concept:** Network-level debugging  

**Exercise 469: Host Network Test**  
**Goal:** Isolate network issue  
**Task:** Run with `--network host`  
**Concept:** Remove network layer  

**Exercise 470: Firewall Issues**  
**Goal:** Check host firewall  
**Task:** Check iptables/firewalld  
**Concept:** Host-level blocking  

---

### Week 48: Image & Build Debugging

**Exercise 471: Build Failure** ⭐  
**Goal:** Debug failed build  
**Task:** Read build output carefully  
**Concept:** Find failing command  

**Exercise 472: Build from Failed Layer**  
**Goal:** Continue debugging  
**Task:** `docker run -it <last-successful-layer> sh`  
**Concept:** Investigate failure point  

**Exercise 473: Build with Progress Output**  
**Goal:** See more detail  
**Task:** `docker build --progress=plain . `  
**Concept:** Full output visibility  

**Exercise 474: Build Cache Issues**  
**Goal:** Cache not working  
**Task:** Check layer ordering  
**Concept:** Cache invalidation  

**Exercise 475: Image Size Analysis**  
**Goal:** Find what's big  
**Task:** `docker history <image>`  
**Concept:** Layer size breakdown  

**Exercise 476: Dive Tool**  
**Goal:** Explore image layers  
**Task:** Use `dive` to analyze  
**Concept:** Visual layer exploration  

**Exercise 477: Compare Images**  
**Goal:** What changed  
**Task:** Compare history of two versions  
**Concept:** Identify differences  

**Exercise 478: Missing Files in Image**  
**Goal:** Debug COPY issues  
**Task:** Check . dockerignore, context  
**Concept:** Build context problems  

**Exercise 479: Permission Denied in Image**  
**Goal:** File permission issues  
**Task:** Check file ownership  
**Concept:** USER instruction effects  

**Exercise 480: Multi-stage Debug**  
**Goal:** Debug multi-stage  
**Task:** Build specific stage, investigate  
**Concept:** Stage-by-stage debugging  

---

### Week 49: Volume & Storage Debugging

**Exercise 481: Volume Not Mounted** ⭐  
**Goal:** Debug mount issues  
**Task:** `docker inspect` check Mounts  
**Concept:** Verify mount configuration  

**Exercise 482: Permission Denied on Volume**  
**Goal:** Permission issues  
**Task:** Check file ownership, container user  
**Concept:** User ID mapping  

**Exercise 483: Data Not Persisting**  
**Goal:** Find where data goes  
**Task:** Verify mount path matches app  
**Concept:** Correct mount target  

**Exercise 484: Volume Full**  
**Goal:** Disk space issues  
**Task:** `docker system df`  
**Concept:** Storage management  

**Exercise 485: Orphaned Volumes**  
**Goal:** Find unused volumes  
**Task:** `docker volume ls -f dangling=true`  
**Concept:** Cleanup orphans  

**Exercise 486: Volume Backup Issues**  
**Goal:** Debug backup  
**Task:** Verify backup container has access  
**Concept:** Volume sharing  

**Exercise 487: Bind Mount Not Syncing**  
**Goal:** File sync issues  
**Task:** Check path, permissions  
**Concept:** Host-container sync  

**Exercise 488: Docker Desktop File Sharing**  
**Goal:** Mac/Windows issues  
**Task:** Configure file sharing settings  
**Concept:** VM file access  

**Exercise 489: Volume Performance**  
**Goal:** Slow volume access  
**Task:** Use named volumes over bind mounts  
**Concept:** Performance optimization  

**Exercise 490: Read-Only Volume Error**  
**Goal:** Can't write  
**Task:** Check `:ro` flag  
**Concept:** Mount options  

---

### Week 50: Daemon & System Debugging

**Exercise 491: Docker Not Starting** ⭐  
**Goal:** Daemon won't start  
**Task:** Check system logs, journalctl  
**Concept:** Daemon logs  

**Exercise 492: Docker Slow**  
**Goal:** Performance issues  
**Task:** Check disk space, memory  
**Concept:** Resource constraints  

**Exercise 493: Docker Socket Permission**  
**Goal:** Permission denied  
**Task:** Add user to docker group  
**Concept:** Group permissions  

**Exercise 494: Daemon Config Error**  
**Goal:** Bad configuration  
**Task:** Validate daemon. json  
**Concept:** JSON syntax  

**Exercise 495: Out of Disk Space**  
**Goal:** Storage full  
**Task:** `docker system prune`  
**Concept:** Cleanup unused  

**Exercise 496: Too Many Open Files**  
**Goal:** ulimit issues  
**Task:** Increase ulimits  
**Concept:** System limits  

**Exercise 497: Container Stuck Stopping**  
**Goal:** Can't stop container  
**Task:** `docker kill <container>`  
**Concept:** Force termination  

**Exercise 498: Docker Events Analysis**  
**Goal:** Track what happened  
**Task:** `docker events --since 1h`  
**Concept:** Event history  

**Exercise 499: System Resource Check**  
**Goal:** Host resource status  
**Task:** Check CPU, memory, disk on host  
**Concept:** Host impacts containers  

**Exercise 500: Create Debug Checklist** 📝 ⭐  
**Goal:** Systematic debugging  
**Task:** Write your debugging procedure  
**Concept:** Methodical troubleshooting  

---

## 🎓 PHASE 11: Advanced Patterns (Exercises 501-550)

### Week 51: Design Patterns

**Exercise 501: Single Process Container** ⭐  
**Goal:** One process per container  
**Task:** Separate app and logger  
**Concept:** Container best practice  

**Exercise 502: Sidecar Pattern** ⭐  
**Goal:** Helper container  
**Task:** Log shipper alongside app  
**Concept:** Augment main container  

**Exercise 503: Ambassador Pattern**  
**Goal:** Proxy container  
**Task:** Local proxy to remote service  
**Concept:** Connection abstraction  

**Exercise 504: Adapter Pattern**  
**Goal:** Interface translator  
**Task:** Convert app output format  
**Concept:** Standardize interfaces  

**Exercise 505: Init Container**  
**Goal:** Initialization tasks  
**Task:** Run setup before main app  
**Concept:** Ordered startup  

**Exercise 506: Process Manager**  
**Goal:** Multiple processes  
**Task:** Use supervisor/s6  
**Concept:** When you need multiple processes  

**Exercise 507: Health Sidecar**  
**Goal:** External health checks  
**Task:** Separate container for health  
**Concept:** Decoupled monitoring  

**Exercise 508: Configuration Sidecar**  
**Goal:** Dynamic config  
**Task:** Container that updates config  
**Concept:** Config management  

**Exercise 509: Service Mesh Intro**  
**Goal:** Understand mesh concept  
**Task:** Read about Istio/Linkerd  
**Concept:** Advanced networking  

**Exercise 510: API Gateway Pattern**  
**Goal:** Single entry point  
**Task:** nginx/traefik as gateway  
**Concept:** Route management  

---

### Week 52: Performance Optimization

**Exercise 511: Minimize Image Size** ⭐  
**Goal:** Smaller images  
**Task:** Multi-stage, alpine, cleanup  
**Concept:** Size matters  

**Exercise 512: Build Cache Optimization**  
**Goal:** Faster builds  
**Task:** Order Dockerfile correctly  
**Concept:** Maximize cache hits  

**Exercise 513: Layer Optimization**  
**Goal:** Fewer layers  
**Task:** Combine RUN commands  
**Concept:** Layer efficiency  

**Exercise 514: Startup Time**  
**Goal:** Faster container start  
**Task:** Minimize init work  
**Concept:** Quick ready time  

**Exercise 515: Resource Requests**  
**Goal:** Right-size containers  
**Task:** Profile and set limits  
**Concept:** Efficient resource use  

**Exercise 516: Connection Pooling**  
**Goal:** Reuse connections  
**Task:** Database connection pools  
**Concept:** Reduce overhead  

**Exercise 517: Caching Strategies**  
**Goal:** Add caching layer  
**Task:** Redis/memcached  
**Concept:** Performance boost  

**Exercise 518: Volume Performance**  
**Goal:** Fast storage  
**Task:** Named volumes vs binds  
**Concept:** Storage speed  

**Exercise 519: Network Performance**  
**Goal:** Optimize networking  
**Task:** Host network for performance  
**Concept:** Network overhead  

**Exercise 520: Monitoring Performance** 📝  
**Goal:** Track metrics  
**Task:** Add Prometheus metrics  
**Concept:** Observability  

---

### Week 53: High Availability

**Exercise 521: Redundancy Planning**  
**Goal:** Eliminate single points  
**Task:** Identify critical components  
**Concept:** Fault tolerance  

**Exercise 522: Stateless Containers** ⭐  
**Goal:** Easy scaling  
**Task:** Externalize all state  
**Concept:** Horizontal scaling  

**Exercise 523: Graceful Shutdown** ⭐  
**Goal:** Handle SIGTERM  
**Task:** Application catches signals  
**Concept:** Clean termination  

**Exercise 524: Health Checks**  
**Goal:** Automatic recovery  
**Task:** Proper health endpoints  
**Concept:** Self-healing  

**Exercise 525: Restart Policies** ⭐  
**Goal:** Auto-restart  
**Task:** `restart: unless-stopped`  
**Concept:** Automatic recovery  

**Exercise 526: Load Balancing**  
**Goal:** Distribute traffic  
**Task:** nginx/HAProxy frontend  
**Concept:** Traffic distribution  

**Exercise 527: Session Handling**  
**Goal:** Sticky sessions  
**Task:** Session store or affinity  
**Concept:** Stateful connections  

**Exercise 528: Database HA**  
**Goal:** Database redundancy  
**Task:** Primary-replica setup  
**Concept:** Data availability  

**Exercise 529: Failover Testing**  
**Goal:** Verify HA works  
**Task:** Kill container, check recovery  
**Concept:** Chaos testing  

**Exercise 530: Backup Site** 📝  
**Goal:** Geographic redundancy  
**Task:** Replicate to another location  
**Concept:** Disaster recovery  

---

### Week 54: Microservices Patterns

**Exercise 531: Service Decomposition**  
**Goal:** Split monolith  
**Task:** Identify bounded contexts  
**Concept:** Service boundaries  

**Exercise 532: API Contracts**  
**Goal:** Service communication  
**Task:** Define clear APIs  
**Concept:** Interface design  

**Exercise 533: Service Discovery**  
**Goal:** Find services  
**Task:** DNS-based discovery  
**Concept:** Dynamic lookup  

**Exercise 534: Circuit Breaker**  
**Goal:** Failure isolation  
**Task:** Implement circuit breaker  
**Concept:** Prevent cascading failure  

**Exercise 535: Retry Logic**  
**Goal:** Handle transient failures  
**Task:** Exponential backoff  
**Concept:** Resilient communication  

**Exercise 536: Timeout Configuration**  
**Goal:** Prevent hanging  
**Task:** Set appropriate timeouts  
**Concept:** Fail fast  

**Exercise 537: Event-Driven**  
**Goal:** Async communication  
**Task:** Message queue pattern  
**Concept:** Loose coupling  

**Exercise 538: Saga Pattern**  
**Goal:** Distributed transactions  
**Task:** Compensating transactions  
**Concept:** Data consistency  

**Exercise 539: CQRS Pattern**  
**Goal:** Separate read/write  
**Task:** Different models for query/command  
**Concept:** Optimized paths  

**Exercise 540: Event Sourcing** 📝  
**Goal:** Event log  
**Task:** Store events, derive state  
**Concept:** Audit and replay  

---

### Week 55: DevOps Integration

**Exercise 541: Infrastructure as Code** ⭐  
**Goal:** Version control infra  
**Task:** All configs in Git  
**Concept:** Reproducible infrastructure  

**Exercise 542: GitOps Workflow**  
**Goal:** Git-driven deployments  
**Task:** Changes via pull requests  
**Concept:** Declarative infrastructure  

**Exercise 543: Environment Parity**  
**Goal:** Same everywhere  
**Task:** Same image, different config  
**Concept:** Dev = Staging = Prod  

**Exercise 544: Feature Branches**  
**Goal:** Branch-based environments  
**Task:** Spin up per-branch  
**Concept:** Isolated testing  

**Exercise 545: Automated Testing**  
**Goal:** Test in pipeline  
**Task:** Unit, integration, e2e  
**Concept:** Quality gates  

**Exercise 546: Continuous Deployment**  
**Goal:** Auto deploy  
**Task:** Deploy on merge  
**Concept:** Fast feedback  

**Exercise 547: Rollback Automation**  
**Goal:** Quick recovery  
**Task:** One-click rollback  
**Concept:** Reduce MTTR  

**Exercise 548: Documentation as Code**  
**Goal:** Docs in repo  
**Task:** README, docs folder  
**Concept:** Up-to-date docs  

**Exercise 549: Runbooks**  
**Goal:** Operational docs  
**Task:** Document procedures  
**Concept:** Knowledge sharing  

**Exercise 550: On-call Procedures** 📝  
**Goal:** Incident response  
**Task:** Define escalation  
**Concept:** Operational readiness  

---

## 🏆 PHASE 12: Capstone Projects (Exercises 551-600)

### Week 56-60: Complete Projects

**Exercise 551: Personal Blog** 📝 ⭐  
**Goal:** Static site deployment  
**Task:** Nginx serving static files  
**Concept:** Simple web hosting  

**Exercise 552: Todo API**  
**Goal:** REST API  
**Task:** Node.js/Python API + database  
**Concept:** Backend development  

**Exercise 553: Full Stack App** ⭐  
**Goal:** Frontend + Backend + DB  
**Task:** React + API + PostgreSQL  
**Concept:** Complete application  

**Exercise 554: E-commerce Platform**  
**Goal:** Complex application  
**Task:** Shop with cart, payments  
**Concept:** Real-world complexity  

**Exercise 555: Chat Application**  
**Goal:** Real-time app  
**Task:** WebSocket chat  
**Concept:** Stateful connections  

**Exercise 556: File Storage Service**  
**Goal:** File handling  
**Task:** Upload, store, serve files  
**Concept:** Binary data handling  

**Exercise 557: Authentication Service**  
**Goal:** Auth system  
**Task:** JWT, OAuth  
**Concept:** Security implementation  

**Exercise 558: Email Service**  
**Goal:** Email sending  
**Task:** SMTP container  
**Concept:** External integrations  

**Exercise 559: Scheduled Jobs**  
**Goal:** Cron jobs  
**Task:** Scheduled tasks  
**Concept:** Background processing  

**Exercise 560: Queue Worker**  
**Goal:** Background workers  
**Task:** Redis queue + workers  
**Concept:** Async processing  

**Exercise 561: Log Aggregation** ⭐  
**Goal:** Centralized logging  
**Task:** ELK/EFK stack  
**Concept:** Observability  

**Exercise 562: Metrics Dashboard**  
**Goal:** Monitoring  
**Task:** Prometheus + Grafana  
**Concept:** Metrics visualization  

**Exercise 563: CI/CD Pipeline** ⭐  
**Goal:** Automated pipeline  
**Task:** Build, test, deploy  
**Concept:** Automation  

**Exercise 564: Development Environment**  
**Goal:** Dev setup  
**Task:** Complete dev compose  
**Concept:** Developer experience  

**Exercise 565: Production Environment**  
**Goal:** Prod setup  
**Task:** Hardened prod compose  
**Concept:** Production readiness  

**Exercise 566: Database Cluster**  
**Goal:** HA database  
**Task:** Primary-replica setup  
**Concept:** Data reliability  

**Exercise 567: Cache Cluster**  
**Goal:** HA cache  
**Task:** Redis cluster  
**Concept:** Cache reliability  

**Exercise 568: Load Balancer Setup**  
**Goal:** Traffic distribution  
**Task:** nginx/HAProxy  
**Concept:** Scaling  

**Exercise 569: SSL/TLS Setup** ⭐  
**Goal:** HTTPS  
**Task:** Certificates and config  
**Concept:** Secure transport  

**Exercise 570: Reverse Proxy** ⭐  
**Goal:** Single entry point  
**Task:** Route to multiple services  
**Concept:** Gateway pattern  

**Exercise 571: API Rate Limiting**  
**Goal:** Protect APIs  
**Task:** Request throttling  
**Concept:** API protection  

**Exercise 572: Web Application Firewall**  
**Goal:** Security layer  
**Task:** WAF configuration  
**Concept:** Application security  

**Exercise 573: Backup System**  
**Goal:** Data protection  
**Task:** Automated backups  
**Concept:** Data safety  

**Exercise 574: Disaster Recovery**  
**Goal:** Recovery plan  
**Task:** Document and test  
**Concept:** Business continuity  

**Exercise 575: Multi-Environment Setup**  
**Goal:** Dev/Stage/Prod  
**Task:** Environment configs  
**Concept:** Environment management  

**Exercise 576: Secret Management**  
**Goal:** Secure secrets  
**Task:** Secret storage  
**Concept:** Security  

**Exercise 577: Health Dashboard**  
**Goal:** System status  
**Task:** Status page  
**Concept:** Visibility  

**Exercise 578: Alerting System**  
**Goal:** Notifications  
**Task:** Alert rules  
**Concept:** Proactive monitoring  

**Exercise 579: Documentation Site**  
**Goal:** API docs  
**Task:** Swagger/OpenAPI  
**Concept:** API documentation  

**Exercise 580: Admin Panel**  
**Goal:** Management UI  
**Task:** Admin interface  
**Concept:** Operations  

**Exercise 581: Testing Suite**  
**Goal:** Comprehensive tests  
**Task:** All test types  
**Concept:** Quality assurance  

**Exercise 582: Performance Testing**  
**Goal:** Load testing  
**Task:** Stress test setup  
**Concept:** Capacity planning  

**Exercise 583: Security Audit**  
**Goal:** Security review  
**Task:** Scan and fix  
**Concept:** Security posture  

**Exercise 584: Cost Optimization**  
**Goal:** Resource efficiency  
**Task:** Right-size resources  
**Concept:** Cost management  

**Exercise 585: Scaling Strategy**  
**Goal:** Growth plan  
**Task:** Horizontal scaling  
**Concept:** Scalability  

**Exercise 586: Migration Plan**  
**Goal:** Move to Docker  
**Task:** Containerize existing app  
**Concept:** Migration  

**Exercise 587: Legacy Integration**  
**Goal:** Connect old and new  
**Task:** Bridge patterns  
**Concept:** Integration  

**Exercise 588: Microservices Split**  
**Goal:** Decompose monolith  
**Task:** Extract services  
**Concept:** Architecture evolution  

**Exercise 589: Service Mesh Basics**  
**Goal:** Advanced networking  
**Task:** Traffic management  
**Concept:** Cloud-native  

**Exercise 590: Observability Stack** ⭐  
**Goal:** Full observability  
**Task:** Logs + Metrics + Traces  
**Concept:** Complete visibility  

**Exercise 591: Chaos Engineering**  
**Goal:** Failure testing  
**Task:** Inject failures  
**Concept:** Resilience  

**Exercise 592: Canary Releases**  
**Goal:** Safe deployments  
**Task:** Gradual rollout  
**Concept:** Risk reduction  

**Exercise 593: Feature Flags**  
**Goal:** Toggle features  
**Task:** Flag system  
**Concept:** Release control  

**Exercise 594: A/B Testing**  
**Goal:** Experiment  
**Task:** Traffic splitting  
**Concept:** Data-driven  

**Exercise 595: Blue-Green Deploy**  
**Goal:** Zero-downtime  
**Task:** Environment switch  
**Concept:** Deployment strategy  

**Exercise 596: Database Migration**  
**Goal:** Schema changes  
**Task:** Safe migrations  
**Concept:** Data evolution  

**Exercise 597: Zero-Downtime Updates**  
**Goal:** Always available  
**Task:** Rolling updates  
**Concept:** Continuous availability  

**Exercise 598: Production Checklist**  
**Goal:** Launch preparation  
**Task:** Verify all items  
**Concept:** Production readiness  

**Exercise 599: Operations Runbook**  
**Goal:** Operational docs  
**Task:** All procedures  
**Concept:** Knowledge base  

**Exercise 600: FINAL PROJECT** 🏆 ⭐  
**Goal:** Complete system  
**Task:** Build production-ready application with:  
- Multiple microservices  
- Database with persistence  
- Cache layer  
- Load balancer  
- SSL/TLS  
- Monitoring & logging  
- CI/CD pipeline  
- Documentation  
- Backup strategy  
**Concept:** Everything you've learned!   

---

## 📚 Learning Tips

### For Complete Beginners:
1. **Do exercises in order** - each builds on previous concepts
2. **Type every command** - don't copy/paste, muscle memory matters
3. **Read error messages** - they usually tell you what's wrong
4. **Take breaks** - 5-10 exercises per day is perfect
5. **Repeat difficult concepts** - marked with 🎯

### When Stuck:
1.  Read the error message carefully
2. Check `docker logs` for container issues
3. Use `docker inspect` for detailed info
4. Search the error online
5. Ask for help with specific error messages

### Marking Your Progress:
- Change ☐ to ✅ when complete
- Add 📝 when you're working on it
- Add 🎯 to exercises you want to practice more

### Study Schedule Suggestion:
- **Week 1-4:** Exercises 1-70 (Basics & Lifecycle)
- **Week 5-8:** Exercises 71-160 (Networking & Volumes)
- **Week 9-13:** Exercises 161-300 (Dockerfile & Compose)
- **Week 14-18:** Exercises 301-400 (Security & Engine)
- **Week 19-23:** Exercises 401-500 (CI/CD & Debugging)
- **Week 24-30:** Exercises 501-600 (Advanced & Projects)

---

## 🎓 What You'll Master

1. **Container Fundamentals** - Images, containers, lifecycle
2. **Networking** - Port mapping, custom networks, DNS
3. **Storage** - Volumes, bind mounts, persistence
4. **Dockerfile** - Build custom images, multi-stage builds
5. **Docker Compose** - Multi-container applications
6. **Security** - Best practices, secrets, scanning
7. **Daemon Configuration** - Storage, logging, contexts
8. **CI/CD** - Automated builds, testing, deployment
9. **Troubleshooting** - Debug containers, networks, storage
10. **Advanced Patterns** - Microservices, HA, DevOps

Good luck on your Docker journey! 🐳













