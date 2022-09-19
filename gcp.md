
```
gcloud compute zones list | grep us-central1



# sets default zone 
gcloud config set compute/zone us-central1-c


gcloud compute instances create "my-vm" \
--machine-type "n1-standard-1" \
--image-project "debian-cloud" \
--image "debian-9-stretch-v20170918" \
--subnet "default"


ping my-vm-1

ssh my-vm-1


sudo apt-get install nginx-light -y

```
