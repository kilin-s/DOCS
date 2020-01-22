

merge jsons 
```console
foo@bar:~$  jq -s '[.[][]]' file*
```

extract rpm
```console
rpm2cpio php-5.1.4-1.esp1.x86_64.rpm | cpio -idmv
```
