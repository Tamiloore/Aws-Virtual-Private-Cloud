# AWS Virtual Private Cloud
## Project Description:
We'll explore the core concept of Amazon Web Service (AWS), focusing specifically on virtual Private Clouds (VPCs)
- Subnets 
- Gateways
- Routing tables
We'll navigate the AWS management console to deploy and manage these critical components effectively. 

## Project Goals: 
- Setting up and configuring VPC, Subnets, internet gateway, NAT gateway
- Enable internet connectivity securely within VPC 
- Implement outbound internet access through the NAT gateway.


## Step 1: Setting up a Virtual Private Cloud (VPC)

- Navigate to the search bar and enter VPC

![1](https://github.com/user-attachments/assets/c229124e-a103-4127-98fd-7e1164bc40ad)


- Navigate to the "Create VPC" option and click on it

![2](https://github.com/user-attachments/assets/c0af1e3e-f341-4b25-90a4-68739597b99b)

- Select the "VPC only" option, specify the IPv4 CIDR block, and proceed by clicking on the "Create VPC" button.

![3](https://github.com/user-attachments/assets/5e394072-87bc-4346-bda7-8a32d8d9e4f1)


Note: If you encounter an error message stating that the CIDR block must be between '/16 and /28' when creating a VPC, it indicates that your provided CIDR block falls outside of this recommended range.

- VPC created
  
![4](https://github.com/user-attachments/assets/09d7baa5-8604-4a38-ac25-5a78bfa29f9c)

## Step 2: Configuring Subnets within the VPC

- Navigate to the "Subnets" option located on the left sidebar.

- Proceed to click on the "Create Subnet" button.

![5](https://github.com/user-attachments/assets/6f7edd8e-7602-43d5-81f7-b75f61696c7c)

- Select the ID of the VPC that you created in the previous step

![6](https://github.com/user-attachments/assets/8bffdae4-a38e-4c82-a287-9e47d46b5a1a)

- Enter the subnet name, and specify the IPv4 CIDR for the subnet.

- choose the availability zone

- Specify the IPv4 CIDR for the subnet 

- To create another subnet, Click on the "Add subnet" button.

![7](https://github.com/user-attachments/assets/514008a7-4b9a-488b-9f32-0cc3ef57520d)

- Repeat the same steps for the second subnet

- Ensuring to specify the subnet name, choose the availability zone, and provide the IPV4 CIDR

![8](https://github.com/user-attachments/assets/a8868aa3-92fc-4d57-a7e1-197bdb22a242)

Your subnets is being created

![9](https://github.com/user-attachments/assets/cd1b3c1d-e18a-4913-a5fb-74b5d2899ddb)

## Step 3: Creating Internet Gateway

- Navigate to the "Internet Gateway"

- Click on the "Create Internet Gateway"

![10](https://github.com/user-attachments/assets/4f56a5f8-dc32-48ae-a2e8-e8ef2a022c41)

- Specify the name of Internet Gateway

- Click on the "Creating Internet Gateway"

![11](https://github.com/user-attachments/assets/06f39827-9ec4-40dc-b7d1-5463a4ae2a41)

Your internet gateway is being successfully created.

![12](https://github.com/user-attachments/assets/fe639577-73ed-436c-a05e-0714cb42ea00)

Now, you will notice that it is currently detached, indicating that it is not associated with any VPC. To enable internet connectivity, you must attach the Internet Gateway to the VPC you have previously created.

Now, attach it to the VPC

![13](https://github.com/user-attachments/assets/75efa73d-b1ba-4d47-9fbe-a4031a6c8fe4)


Successfully attached 

![14](https://github.com/user-attachments/assets/0f039d05-1007-49ba-a9cd-077483b62e21)

## Step 4: Creating Route Tables

Let's come to the next part which is enabling internet connectivity with the internet Gateway by setting up routing tables

- Proceed to the " Route Tables"

- Click on the "Create route table

![15](https://github.com/user-attachments/assets/b7da125b-8cc2-4def-92f6-52bd22af5683)

- Enter the name of the route table and select the VPC you previously created 

- Create a route table

![16](https://github.com/user-attachments/assets/676770cc-2fe9-43e8-bdde-9ea9a7170978)


- Click on "Subnet association" followed by "edit subnet associations" to associate the subnet with the route table

![17](https://github.com/user-attachments/assets/3a4aa8c6-f65d-4ab3-bfb6-3853886db84c)

- Choose the public subnet and click on Save association.

![18](https://github.com/user-attachments/assets/f79d5620-b939-4487-be5e-795a8c9915ba)


- Navigate to "Routes" and then click on "Edit routes" 

![19](https://github.com/user-attachments/assets/1ff9c88f-ad70-40a0-b944-6dd6a3998777)

- Click on add route 

- Select "Destination" as "0.0.0.0/0", indicating that every IPV4 address can access this subnet

- "Target Field", Choose "Internet Gateway" and then select the Internet Gateway you created. finally, save the changes.

![20](https://github.com/user-attachments/assets/9016e503-19b8-4033-88fd-3df80ff4e3bc)


![21](https://github.com/user-attachments/assets/29dcde60-e1fe-4779-8769-25faeb7b1c8f)


## Step 5: Creating NAT Gateway

- Navigate to the "NAT Gateways" then click on "Create NAT Gateway"

![22](https://github.com/user-attachments/assets/289b21d7-6362-4f95-9f9b-67f0310fef90)

- Choose the Private subnet 

- Select the connectivity type as private

- Create NAT Gateway

![23](https://github.com/user-attachments/assets/9e18f309-5d32-4f48-8583-f908d9cd9e77)

Your NAT Gateway is being created successfully 

- Select your NAT Gateway.

- Navigate to the " Details tab

- Locate the subnet ID and click on it

![24](https://github.com/user-attachments/assets/1a500a83-f7f5-4137-b027-15784ec0ece2)

- Navigate to the "Route Table" section. 

- Then click on the "route table ID"

![25](https://github.com/user-attachments/assets/4c5197e6-d668-4d8d-b9a6-aa15f41885f0)

- Proceed to the "Routes" section, then click on "Edit routes"

![26](https://github.com/user-attachments/assets/1b76432b-16ed-466b-ae13-8fe2a63b7822)

- Then click on "Add routes"

- Select "Destination" as "0.0.0.0/0" 

- In the  "Target" field, choose the "NAT Gateway you created.

- Finally, save the changes 

![27](https://github.com/user-attachments/assets/89c9adf5-ca0a-4eff-97b7-0b33dc3ce611)

- On the subnet association section,  click on the edit subnet association

![28](https://github.com/user-attachments/assets/3483598a-4f5c-4234-9960-bf1a32625f34)

- Choose the private subnet and click on "Save associations" 

![29](https://github.com/user-attachments/assets/305f9d3a-c028-40bb-a667-65ba5576d4b9)

The subnet has been successfully attached to the route table 

![30](https://github.com/user-attachments/assets/5b4f5347-e286-4eb0-a008-da866a19a843)











