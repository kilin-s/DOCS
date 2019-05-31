

delete all untaget images

```console
foo@bar:~$ docker image rm $(docker image ls --format "{{.ID}}" --filter "dangling=true")
```
