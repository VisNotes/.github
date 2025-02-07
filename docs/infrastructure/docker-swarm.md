# Docker Manual Deployment

**Create network**

```bash
docker network create --driver overlay ocr-net
```

1. init swarm

```bash
docker swarm init
```

2. Create postgres secret

```bash
printf <PASSWORD HERE> | docker secret create POSTGRES_PASSWORD -
```

3. Deploy
```bash
docker stack deploy -c swarm.yml ocr-api
```

4. Check
```bash
docker stack services ocr-api
```


## Adding CI/CD Pipeline (With Docker and Github Actions)

### Prerequisites

1. A Dockerfile in the root of the repo
2. A docker-stack.yml file in the root of the repo
3. A docker hub account and a repository for the image
4. A secret in the repo for the docker hub username and a PAT for the docker hub password

### Create a User for Deploying

1. Switch to root and add a new User

```bash
sudo adduser deploy-<container_name/repo>
```

2. Add user to docker group

```bash
sudo usermod -aG docker deploy-<container_name/repo>
```

3. Switch to new user

```bash
su - deploy-<container_name/repo>
```

4. Create an SSH key (Recommend to generate the ssh key on your local machine and create the private key as a secret in the repo)

```bash
# On Remote Machine
mkdir ~/.ssh

  
# On Local Machine
ssh-keygen -t ed25519 -C "deploy-<container_name/repo>@<host>"

# Copy the public key clipboard
## windows
cat ~/.ssh/id_ed25519.pub | clip
## linux
cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard

# On Remote Machine
echo '<public_key>' > ~/.ssh/authorized_keys
```
5. Restrict deploy user to only use the docker command

```bash
nano ~/.ssh/authorized_keys

# Prepend the key with the following
command="docker system dial-stdio"
```
**You should no longer be able to ssh via the deploy user**
*Check pipeline for how to use docker stack to deploy*


# Helpful Docker Commands

**To investigate a service**

```bash
docker service ps <service_name>
```

***Cleanup***
```bash
 docker stack rm <stack_name>
```
**Restart docker**
```bash
sudo systemctl restart docker
```

**View logs**
```bash
docker service logs --follow <service_name>
```
