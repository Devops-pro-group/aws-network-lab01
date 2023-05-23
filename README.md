Topic: Create Aws network resource == VPC - VPC-Peering

# aws-network-lab01
# VPC-A
# I-Create a VPCA
    A =====> 10.0.0.0/16
# II Create four subnets ( 2 publics and 2 privates) for VPCA
   sub-Pub0 ====> 10.0.0.0/24
   sub-Pub1 ====> 10.0.1.0/24
   
   sub-Priv0 ====> 10.0.2.0/24
   sub-Priv1 ====> 10.0.3.0/24
 # III -Route Tabe( 2 routes table : public and private) for VPCB
     public ====> 0.0.0.0/0
      private ===> /16
 # IV Internetegateway 
     ==> Attached to vpc A
 # V Security Group 
      Allow all traffic 
  # VI Launch an instance and echo a custom message
       - launch ec2 and have an http with Hello from VPC-A on vpc A
  ########################################################################################
 # VPC _B
 #  I-Create a VPCB
    B =====> 172.0.0.0/16
 # II Create two subnets ( 1 publics and 2 privates) for VPCB
      Sub-Pub-vpcB  172.0.0.0/24
       Sub-Priv-vpcB  172.0.1.0/24  
 # III -Route Tabe( 2 routes table : public and private) for VPCB
     public ====> 0.0.0.0/0
      private ===> /16
  # IV Internetgateway 
     ==> Attached to vpc 
   # V Security Group 
      Allow all traffic 
 
   
# VI Launch ec2 instance 
#   Install httpd
      - sudo yum install httpd -y
      - sudo systemctl start httpd
      - sudo systemctl status hpptd
      - launch ec2 and have an http with Hello from VPC-B on vpc b
    
# Create vpc peering 
       name my-peering
       Request peering
       Accept peering 
       Edit route table for both vpc 
# Check Vpc peering 
      ssh an ec2 instance in vpc and do:
      curl ipaddress(instance in vpc b)


  
 
