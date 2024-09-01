# AWS Virtual Private Cloud
## Project Description:
We'll explore the core concept of Amazon Web Service (AWS), focusing specifically on virtual Private Clouds (VPCs)
- Subnets 
- Gateways
- Routing tables
We'll nagivate the AWS management console to deploy and manage these critical component effectively. 

## Project Goals: 
- Setting up and configuring VPC, Subnets, internet gateway, NAT gateway, and VPC peering connections 
- Enable internet connectivity securely within VPC 
- Implement outbound internet access through the NAT gateway.
- Establish direct communication between VPCs using VPC peering

## Step 1: Setting up a Virtual Private Cloud (VPC)

- Navigate to the search bar and enter VPC

![alt text](img/1.png)

- Navigate to the "Create VPC" option and click on it

![alt text](img/2.png)

- Select the "VPC only" option, specify the IPv4 CIDR block, and proceed by clicking on the "Create VPC" button.

![alt text](img/3.png)

Note: If you encouter an error messege stating that the CIDR block must be between '/16 and /28' when creating a VPC, it indicates that your provided CIDR block falls outside of this recommended range.

- VPC created
![alt text](img/4.png)

## Step 2: Configuring Subnets within the VPC

- Navigate to the "Subnets" option located on the left sidebar.

- Proceed to click on the "Create Subnet" button.

![alt text](img/5.png)

- Select the ID of the VPC that you created in the previous step

![alt text](img/6.png)

- Enter the subnet name, specify the IPv4 CIDR for the subnet.

- choose the availability zone

- Specify the IPv4 CIDR for the subnet 

- To create another subnet, Click on the "Add subnet" button.

![alt teAws-Virtual-Private-Cloud/img/7.pngxt](img/7.png)


- Repeat the same steps for the second subnet

- Ensuring to specify the subnet name, choose the availabilty zone, and provide the IPV4 CIDR

![alt text](img/8.png)


Your subnets is being created

![alt text](img/9.png)


## Step 3: Creating Internet Gateway

- Navigate to the "internet Gateway"

- Click on the "Create Internet Gateway"

![alt text](img/10.png)

- Specify the name of Internet Gateway

- Click on the "Creating Internet Gateway"

![alt text](img/11.png)

Your internet gateway is being successfully created.

![alt text](img/12.png)

Now, you will notice that it is currently detached, indicating that it is not associated with any VPC. To enable internet connectivity, you must attach the internet Gateway to the VPC you have previously created.

Now, attach it to the VPC

![alt text](img/13.png)

Succefully attached 

![alt text](img/14.png)


## Step 4: Creating Route Tables

Let's come to the next part which is enabling internet connectivity with the internet Gateway by setting up routing tables

- Proceed to the " Route Tables"

- Click on the "Create route table

![alt text](img/15.png)

- Enter the name of the route table and select the VPC you previously created 

- Create route table

![alt text](img/16.png)

- Click on "Subnet association" followed by "edit subnet associations" to associate the subnet with the route table

![alt text](img/17.png)

- Choose the public subnet and click on Save association.

![alt text](img/18.png)

- Navigate to "Routes" and then click on "Edit routes" 

![alt text](img/19.png)

- Click on add route 

- Select "Destination" as "0.0.0.0/0", indicating that every IPV4 address can access this subnet

- "Target Field", Choose "Internet Gateway" and then select the internet Gateway you created. finally save the changes.

![alt text](img/20.png)

![alt text](img/21.png)

## Step 5: Creating NAT Gateway

- Navigate to the "NAT Gateways" then click on "Create NAT Gateway"

![alt text](img/22.png)

- Choose the Private subnet 

- Select the connectivity type as private

- Create NAT Gateway

![alt text](img/23.png)

Your NAT Gateway is being created successfully 

- Select your NAT Gateway.

- Navigate to the " Details tab

- Locate the subnet ID and click on it

![alt text](img/24.png)








