# [Stephen Grider] Docker and Kubernetes: The Complete Guide [2018, ENG]


**Original src**:  
https://github.com/StephenGrider/DockerCasts


<br/>

### 09 Dockerizing Multiple Services

<br/>

![Application](/img/pic-09-01.png?raw=true)

<br/>

![Application](/img/pic-09-02.png?raw=true)

<br/>

![Application](/img/pic-09-03.png?raw=true)

<br/>

    $ cd 01-complex/client/
    $ docker build -f Dockerfile.dev .
    Successfully built 05efd9c2ea0c

    $ cd ../server/
    $ docker build -f Dockerfile.dev .
    Successfully built 2a1c5f2e40a7

    $ cd ../worker/
    $ docker build -f Dockerfile.dev .
    Successfully built 772a168e89a0


<br/>

![Application](/img/pic-09-04.png?raw=true)

<br/>

![Application](/img/pic-09-05.png?raw=true)

<br/>

![Application](/img/pic-09-06.png?raw=true)


        $ docker-compose up --build

<br/>

![Application](/img/pic-09-07.png?raw=true)


http://localhost:8080/api/values/current


```shell
$ docker-compose ps
        Name                     Command            State          Ports        
--------------------------------------------------------------------------------
01-complex_api_1        npm run dev                 Up                          
01-complex_client_1     npm run start               Up                          
01-complex_nginx_1      nginx -g daemon off;        Up      0.0.0.0:8080->80/tcp
01-complex_postgres_1   docker-entrypoint.sh        Up      5432/tcp            
                        postgres                                                
01-complex_redis_1      docker-entrypoint.sh        Up      6379/tcp            
                        redis ...                                               
01-complex_worker_1     npm run dev                 Up                          
```

---

**Marley**

<a href="https://jsdev.org">jsdev.org</a>  