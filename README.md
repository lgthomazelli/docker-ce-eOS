## Install Docker-CE + Docker Compose on elementary OS

### 1 - Install Docker-CE

##### <i class="icon-code"></i> Update **apt** package
```{r, engine='bash', count_lines}
sudo apt-get update
```

##### <i class="icon-code"></i> Install packages to allow **apt** to use a repository over HTTPS:
```{r, engine='bash', count_lines}
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

##### <i class="icon-code"></i> Add **Docker’s** official GPG key:
```{r, engine='bash', count_lines}
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

##### <i class="icon-code"></i> Use the following command to set up the **stable** repository:
```{r, engine='bash', count_lines}
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -u -cs) \
   stable"
```

##### <i class="icon-code"></i> Update **apt** package
```{r, engine='bash', count_lines}
sudo apt-get update
```

##### <i class="icon-code"></i> Install **docker-ce** version:
```{r, engine='bash', count_lines}
sudo apt-get install docker-ce
```

### 2 - Install Docker Compose

##### <i class="icon-code"></i> Use the following command to download the latest version of **Docker Compose**:
```{r, engine='bash', count_lines}
sudo curl -L https://github.com/docker/compose/releases/download/1.17.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```

##### <i class="icon-code"></i> Apply executable permissions to the binary:
```{r, engine='bash', count_lines}
sudo chmod +x /usr/local/bin/docker-compose
```

##### <i class="icon-code"></i> Test the installation:
```{r, engine='bash', count_lines}
docker-compose --version
```
