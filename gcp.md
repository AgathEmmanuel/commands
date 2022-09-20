# gcloud




## logout from an account on gcloud SDK

```
# to logout from all the accounts 
gcloud auth revoke --all

# logout from a specific account
gcloud auth revoke <your_account>

# login with a different account
gcloud auth login

```


## Manage multiple gcloud config configurations  

```
gcloud config configurations create pythonrocks
gcloud config configurations list
gcloud config configurations activate pythonrocks
gcloud config set core/account pythonrocks@gmail.com
gcloud projects list
gcloud config set project mygcp-demo

```

## Managing Credentials

```
# List all credentialed accounts.
gcloud auth list
# to authenticate with a user identity (via web flow) which then authorizes gcloud and other SDK tools to access Google Cloud Platform.
gcloud auth login
# Display the current account's access token.
gcloud auth print-access-token

gcloud auth application-default login
gcloud auth application-default  print-access-token
# Service Account: to authenticate with a user identity (via a web flow) but using the credentials as a proxy for a service account.
gcloud auth activate-service-account --key-file=sa_key.json
# use GOOGLE_APPLICATION_CREDENTIALS pointing to JSON key

export GCP_REGION="us-east1"
gcloud auth configure-docker ${GCP_REGION}-docker.pkg.dev
```

## Zones and Regions

```

gcloud compute zones list --filter=region:us-central1
# list regions
gcloud compute regions list

```


## Organization

```
gcloud organizations list

# for a single org, get its id
ORG_ID=$(gcloud organizations list --format 'value(ID)')


# list top level projects
gcloud projects list --filter "parent.id=$ORG_ID AND  parent.type=organization"



# list top level folders
gcloud resource-manager folders list --organization=$ORG_ID
# list sub folders given upper level folder id
gcloud resource-manager folders list --folder=$FOLDER_ID
# get iam policy for the folder
gcloud resource-manager folders get-iam-policy $FOLDER_ID


```


## Billing

```
gcloud beta billing accounts list

# enable a billing account with a project, assuming the user or service account has "Billing Account User" role. 
gcloud beta billing projects link ${project_id} \
            --billing-account ${ORGANIZATION_BILLING_ACCOUNT}

```





## setting up a new vm with nginx

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

sudo vi /var/www/html/index.nginx-debian.html

curl http://localhost/

exit

curl http://my-vm/





```


## Containers

```
gcloud container clusters create k1




```





# Links

[https://gist.github.com/pydevops/cffbd3c694d599c6ca18342d3625af97#01-references](https://gist.github.com/pydevops/cffbd3c694d599c6ca18342d3625af97#01-references)  
[https://cloud.google.com/sdk/gcloud/reference](https://cloud.google.com/sdk/gcloud/reference)  
[https://cloud.google.com/sdk/gcloud](https://cloud.google.com/sdk/gcloud)  
[https://cloud.google.com/sdk/docs/cheatsheet](https://cloud.google.com/sdk/docs/cheatsheet)  

