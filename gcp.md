# gcloud


## creating a gke cluster
```
export MY_ZONE=us-central1-f

gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2

```

## Deployment manager
```
export MY_ZONE=us-central1-f

echo $DEVESHELL_PROJECT_ID

vi mydeploy.yaml
# deployment yaml to create a compute instance



sed -i -e 's/PROJECT_ID/'$DEVESHELL_PROJECT_ID/ mydeploy.yaml
sed -i -e 's/ZONE/'$MY_ZONE/ mydeploy.yaml


gcloud deployment-manager deployments create my-first-deploy \
--config mydeploy.yaml

gcloud deployment-manager deployments list

gcloud deployment-manager deployments update my-first-deploy \
--config mydeploy.yaml



# linux command that creates artificial cpu load on the virtual machine
# its forcing the cpu to continously compress random data
dd if=/dev/urandom | gzip -9 >> /dev/null &


# enabling the cloudprofiler service
gcloud services enable cloudprofiler.googleapis.com
# adding googlecloudprofiler to python application
import googlecloudprofiler
# adding app.yaml
app.yaml
----
runtime: python37
----
gcloud app create --region=us-central
gcloud app deploy --version=one --quiet
# apache bench to generate requests  and traffic from a separate instance
sudo apt install apache2-utils -y
# run apach bench 1000 times
ab -n 1000 -c 10 https://example.com/






#  Connecting to a google kubernetes engin cluster
$HOME/.kube/config
gcloud container clusters get-credential cluster-name --zone zone-name


k apply -f deployment-file
OR
k run deployment-name \
--image image:tag \
--replicas 3 \
--labels key=value \
--port 8080
--generator deployment/apps.v1 \
--save-config

k get deployment deployment-name -o yaml > deploy.yaml


k describe deploy deploy-name

k scale deploy deploy-name --replicas=5

# to create an hpa ( horizontal pod autoscaler )
k autoscale deploy deploy-name --min=5 --max=15 --cpu-percent=75

k apply -f deploy.yaml

k set image deploy deploy-name image image-name:tag

k edit deploy deploy-name

# blue green deployment   for moving v1 to v2
kind: Service
spec:
    selector:
      app: my-app
      version: v1

k create -f my-app-v2.yaml
# traffic will be directed to newer set of pods with version v2
k patch service my-app-service -p '{"spec":{"selector":{"version":"v2"}}}'
# the blue deployment with older version is then deleted


# canary deployments   in starting a subset of traffic is redirected to the new version
# ones stability of new version is confirmed entire traffic is redirected
kind: Service
spec:
    selector:
      app: my-app

k apply -f my-app-v2.yaml
k scale deploy/my-app-v2 --replicas=10
k delete -f my-app-v1.yaml

# Other strategies  A/B testing or shadow testing

# Rolling back a deployment
k rollout undo deploy deploy-name

k rollout undo deploy deploy-name --to-revision=2

k rollout history deploy deploy-name --revision=2

# Clean up policy
- default: 10 revision
- change: .spec.revisionHistoryLimit

k rollout pause deploy deploy-name

k rollout resume deploy deploy-name

k rollout status deploy deploy-name










# Choosing the right strategy
- recreate
- rolling update
- blue/green
- canary
- A/B
- shadow










```

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

