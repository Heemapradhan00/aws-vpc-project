# AWS VPC Setup Project

This project provides step-by-step instructions for creating a custom Virtual Private Cloud (VPC) in AWS with public and private subnets. The setup includes creating and configuring a VPC, subnets, an Internet Gateway, route tables, and testing the configuration.

---

## Features
- **Custom VPC Creation**: Configure a VPC with a specified CIDR block.
- **Subnets**: Create both public and private subnets.
- **Internet Gateway**: Enable internet access for the public subnet.
- **Route Tables**: Manage routing for public and private subnets.
- **EC2 Testing**: Verify connectivity by launching instances.

---

## Prerequisites
- An AWS account.
- Basic knowledge of AWS Networking concepts.
- AWS Management Console access.

---

## Setup Instructions

### **Step 1: Create a VPC**
1. Log in to the AWS Management Console.
2. Go to the **VPC Dashboard**.
3. Click on **Create VPC**.
4. Provide:
   - **Name**: Name your VPC.
   - **CIDR Block**: E.g., `10.0.0.0/16`.
5. Leave the default settings and click **Create**.

---

### **Step 2: Create Subnets**
1. Navigate to the **Subnets** section in the VPC Dashboard.
2. Click **Create Subnet**.
3. Provide:
   - **VPC**: Select the VPC you created.
   - **Subnet Name**: E.g., Public Subnet.
   - **CIDR Block**: E.g., `10.0.1.0/24`.
4. Repeat for the private subnet using a different CIDR block (e.g., `10.0.2.0/24`).

---

### **Step 3: Add an Internet Gateway**
1. Go to the **Internet Gateways** section.
2. Click **Create internet gateway** and give it a name.
3. Attach the Internet Gateway to your VPC:
   - Select the created Internet Gateway.
   - Click **Actions** → **Attach to VPC** → Select your VPC → **Attach**.

---

### **Step 4: Set Up Route Tables**
1. Navigate to the **Route Tables** section.
2. Create two route tables:
   - **Public Route Table**:
     - Associate it with the public subnet.
     - Add a route for internet traffic:
       - Destination: `0.0.0.0/0`
       - Target: Internet Gateway.
   - **Private Route Table**:
     - Associate it with the private subnet.
     - Leave it as is (no internet route).

---

### **Step 5: Test the Configuration**
- **Public Subnet**:
  - Launch an EC2 instance in the public subnet.
  - Verify internet connectivity by SSH-ing into the instance.
- **Private Subnet**:
  - Launch an EC2 instance in the private subnet.
  - Confirm it does not have internet access unless explicitly configured.

---

## Directory Structure
```plaintext
aws-vpc-project/
├── README.md   # Project overview and instructions
├── images/     # (Optional) Add any setup screenshots here
└── scripts/    # (Optional) Automation scripts or configuration files
```

---

## Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue for suggestions and improvements.

---

## License
This project is licensed under the [MIT License](LICENSE).

### Steps to Add to GitHub
1. Save this content in a file named `README.md` in your project directory.
2. Follow the steps outlined in my earlier response to push your project to GitHub.
   ![image](https://github.com/user-attachments/assets/a0f96179-3374-4157-b214-0aba86998bd5)


