# Run the project Locally

In this lecture we will use the `docker compose` which is installed as part of `docker`.

Just go to the directory of cloned repo and run `docker compose up`.

Video of the lecture is self explanatory.

 If we have lauch an EC2 instance and storage is 8 GB then we receive a error 
### write /var/lib/docker/tmp/GetImageBlob2962295582: no space left on device
To Resolve this , first we have to go to Instance--- Storage and Increase the size from 8 GB to 30GB, 
it will take some time to modify(15-20 minutes) when status is ##in-use##
then we have to run below commands

```
df -h
lsblk
```

## Now we have to Install Cloud guest install 

```
sudo apt install cloud-guest-utils
sudo growpart /dev/xvda 1
sudo resize2fs /dev/xvda1
```

### now you can see file size is grow and now you can run command to test App locally

```
docker compose up
```
