# Mongo Cookbook

This repository contains a chef cookbook which provisions a mongodb environment using chef's configuration management tools. Cookbook includes ChefSpec and Chef Inspec tests.

## Prerequisites
I have run the cookbook using the below packages and versions:
- Chef Workstation:
  - Infra Client v15.7.32
  - ChefDK v4.7.73
  - Test Kitchen v2.3.4
  - Foodcritic v16.2.0
  - Cookstyle v5.20.0
- Vagrant v2.2.7
- Git v2.24.1
- VirtualBox v6.1.4
- AWS CLI v2
- AWS account

## Chef

Chef has been used to configure an environment. It is a configuration management tool that allows you to set up the prerequisites of an environment to your needs. It allows a user to configure these environments using code rather than manually creating them which allows automation of configuring machines on a large-scale.

## Cookbook
After cloning this repository, navigate to within the cookbook and follow the below steps.

### Tests
Before creating an environment we can test the cookbook using ChefSpec and Chef Inspec.

#### ChefSpec
We can run the below to test what has been included in the recipe:
```bash
chef exec rspec
```

#### Chef Inspec
We can also run the below to test whether the recipe has run correctly and all configurations are complete:
```bash
kitchen test
```

#### Chef Inspec (Cloud)
The below code is used to run Chef Inspec in the cloud. In our case, '.kitchen9.yml' is set-up to use AWS. The driver settings inside '.kitchen9.yml' should be changed to what is needed e.g subnet_id, region etc.
```bash
KITCHEN_YAML=.kitchen9.yml kitchen test
```

### Running the Cookbook
If all tests have passed you can continue forward and use the cookbook to create a machine image (AMI in AWS) using packer which will not be shown here.

## Author
**Kevin Monteiro** - *DevOps Engineer* - [km-aero](https://github.com/km-aero)
