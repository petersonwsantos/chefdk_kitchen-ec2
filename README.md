# Docker Hub - ChefDK with Kitchen AWS EC2

#  Docker image

Supported tags and respective Dockerfile links

Base Image    |     Tag     |  Backed |  Dockerfile      |  Status
------------|-------------|--------|------------------|-------------------------------------
ubuntu:16.04   | latest      |  chefdf=2.3.4  awscli.version=1.11.187 |( [ Dockerfile ](https://github.com/petersonwsantos/chefdk_kitchen-ec2/blob/master/Dockerfile) ) | xx



How to Use: 
```
$ cd my_dev_code/

$ docker run -it --name chef_playground \
   -v ~/.ssh:/root/.ssh \
   -v ~/.aws:/root/.aws \
   --mount type=bind,source="$(pwd)",target=/cookbook \
    petersonwsantos/chefdk_kitchen-ec2
```

```
Explanation command above:

   ```
      -v ~/.aws:/root/.aws \
       # Creates a volume for my awscli credentials created earlier in my notebook. If you prefer you can take this line and run "awcli configure " directly in the container.
   ```
  
  
   ```
    -v ~/.ssh:/root/.ssh \
`
      # Creates volume for my authentication key, that will be used in ".kitchen.yml"
      ( ssh_key:~/.ssh/key_aws_ec2 ).
   ```


   ```
     --mount type=bind,source="$(pwd)",target=/cookbook \
   
    # Mount volume for my cookbooks's code ( $ cd my_dev_code/ ).    
   ```
