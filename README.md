# Google Cloud and Terraform for Beginners

### Prerequisites 

_cmd or ctrl click to open in new tab_
> * [Google Cloud](https://cloud.google.com/free) Account
> * [Google Cloud SDK]() Installed
> * [Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli) Installed


## Create the Terraform Service Account in Google Cloud

```
PROJECT_ID=$(gcloud config get-value project)
SERVICE_ACCOUNT_ID=sa-terraform-beginners
```

```
gcloud iam service-accounts create sa-terraform-beginners \
--description="Used by Terraform to provision Infrastructure" \
--display-name="Terraform Service Account"
```

```
gcloud iam service-accounts list
```

```
gcloud projects add-iam-policy-binding ${PROJECT_ID} \
    --member="serviceAccount:${SERVICE_ACCOUNT_ID}@${PROJECT_ID}.iam.gserviceaccount.com" \
    --role="roles/editor"
```

```
gcloud iam service-accounts keys create terraform-key.json \
   --iam-account=${SERVICE_ACCOUNT_ID}@${PROJECT_ID}.iam.gserviceaccount.com
```

## Build Shit with Terraform!

```
cd terraform
```

```
terraform init
```

```
terraform plan
```

```
terraform apply
```

```
terraform show
```

```
terraform destroy
```