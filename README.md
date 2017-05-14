# Mycroft Docker Development Environment

### How to build and run

1. Git pull this repository - ```git clone https://github.com/MycroftAI/docker-mycroft.git```

2. Build the docker image with 
   ```docker build -t <yourusername>/mycroft .``` in the directory that you have checked out.

3. If you would rather have an interactive session (for testing, coding, or whatever) with the docker container, start the container with the following, then you would need to start mycroft with the /mycroft/ai/mycroft.sh script.
   ```docker run --device /dev/snd:/dev/snd --privileged -it <youruser>/mycroft /bin/bash```
   
4. Otherwise run the following to start up mycroft and an active cli session in the container:
   ```docker run --device /dev/snd:/dev/snd -d -it <\youruser\>/mycroft```

5. Confirm via docker ps that your container is up and serving port 8000:


```
docker ps
CONTAINER ID        IMAGE                                                COMMAND                  CREATED             STATUS              PORTS                                            NAMES
692219e23bf2        user/mycroft                                    "/mycroft/ai/mycro..."   3 seconds ago       Up 1 second         8000/tcp                                         amazing_borg
```


```
Quickly start, stop or restart Mycroft's esential services in detached screens

usage: /mycroft/ai/mycroft.sh [-h] (start [-v|-c]|stop|restart)
      -h             this help message
      start          starts mycroft-service, mycroft-skills, mycroft-voice and mycroft-cli in quiet mode
      start -v       starts mycroft-service, mycroft-skills and mycroft-voice
      start -c       starts mycroft-service, mycroft-skills and mycroft-cli in background
      start -d       starts mycroft-service and mycroft skills in quiet mode and an active mycroft-cli
      stop           stops mycroft-service, mycroft-skills and mycroft-voice
      restart        restarts mycroft-service, mycroft-skills and mycroft-voice

screen tips:
            run 'screen -list' to see all running screens
            run 'screen -r <screen-name>' (e.g. 'screen -r mycroft-service') to reatach a screen
            press ctrl + a, ctrl + d to detace the screen again
            See the screen man page for more details
```

