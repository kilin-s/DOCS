

#extend vda1 partition
growpart /dev/vda 1
resize2fs /dev/vda1
