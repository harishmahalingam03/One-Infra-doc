## Step: 1
### To Create the infra structure using terraform clone aura-cloud repo from github to your powershell
```
git clone https://<git-hub-token>@github.com/atomedgesoft/aura-middleware.git
```
![image](https://github.com/user-attachments/assets/f57f8b4a-8660-4d72-846b-bdaf02bc6f40)

## Step: 2 
### Verify AWS cli and terraform is installed in your system also verify aws configured with your access and secret key
```
terraform -v
awscli --version
```
![image](https://github.com/user-attachments/assets/0285dbf9-8cf0-4476-8872-f8a9aa0b161b)

## Step: 3
### To initialize the infra to particular environment (DEV,STAGE,PROD) using the terraform change to the aura-cloud directory and execute below command for the specific infra
#### Dev -
```
terraform init -backend-config="bucket=aura-backup-bucket" -backend-config="key=dev-account/terraform.tfstate" -backend-config="region=ap-south-1"
```
#### Stage - 
```
terraform init -backend-config="bucket=aura-backup-bucket" -backend-config="key=stage-account/terraform.tfstate" -backend-config="region=ap-south-1"
```
#### Prod - 
```
terraform init -backend-config="bucket=aura-backup-bucket" -backend-config="key=prod-account/terraform.tfstate" -backend-config="region=ap-south-1"
```
## Example : Initiated infra in the DEV account

 ![image](https://github.com/user-attachments/assets/227fa2e3-2d2a-4929-9e73-0c56fdb98fb1)

## Step: 4
### verify the worksapce where the infra is being initiated list and select the workspace where you want initiate the infra-structure
![image](https://github.com/user-attachments/assets/98875e6c-26eb-4922-bf07-d14b7f7eb9ec)

## Step: 5
#### i)  Execute terraform plan to start the dry run ensure that it does not have any error 
#### ii) Also verify that the access and the secret key are passed correctly if not kindly pass the access and the sceret key for account you wants to have the infra

![image](https://github.com/user-attachments/assets/13f8d6a9-ff12-43aa-9d48-b661ce406b32)
![image](https://github.com/user-attachments/assets/739506ea-3464-45cc-979c-b9f74c6e782b)

## Step: 6 
#### Once all dry runs are passed successfully execute terraform apply to create the infra structure
#### Example here the infra is created in ap-south-1 mumbai region 
```
terraform apply -var="region=ap-south-1" --auto-approve
```











