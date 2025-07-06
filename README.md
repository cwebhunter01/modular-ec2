# 🧱 Modular EC2 Web App Deployment with Terraform (AWS Free Tier)

> 🚀 A production-style, modular Infrastructure as Code (IaC) project using **Terraform**, deployed on **AWS Free Tier**, with remote state management, reusable modules, and clustered EC2 web servers running NGINX.

---

## 📌 What This Project Does

- Provisions **multiple EC2 instances** using a **Terraform module**
- Uses **Amazon S3** for **remote state storage**
- Uses **DynamoDB** for **state locking**
- Boots each EC2 instance with **NGINX via user data**
- Runs 100% on **AWS Free Tier (t2.micro)**
- Exposes instance public IPs via **Terraform outputs**

---

## 📸 Screenshot

![EC2 Dashboard](./Asset/aws.png)  
![VS Code](./Asset/code.png)


## 🗂️ Project Structure

```bash
terraform-day5-modularized/
├── main.tf              # Root module entrypoint
├── variables.tf         # Declares input variables
├── terraform.tfvars     # Sets actual values
├── backend.tf           # Remote backend setup (S3 + DynamoDB)
├── outputs.tf           # Outputs the instance IPs
└── modules/
    └── ec2-instance/
        ├── main.tf      # EC2 logic with user_data
        ├── variables.tf # Input definitions
        └── outputs.tf   # Public IP output

  Tool           Purpose                                  
   
 Terraform     >    Infrastructure as Code (IaC)             
 AWS EC2       >    Cloud compute (Ubuntu 22.04)             
 NGINX         >    Web server (auto-installed via bash)     
 AWS S3        >   Terraform remote state storage           
 AWS DynamoDB  >   State locking to prevent concurrent runs 

 