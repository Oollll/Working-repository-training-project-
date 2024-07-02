# How to launch Terraform infrastructure in a GitHub repository 

#### Step 1 
```
git filter-branch --tree-filter 'rm -rf .terraform' HEAD
```

#### Step 2
```
touch .gitignore
```
##### Contents of .gitignore
```
# Local .terraform directories
**/.terraform/*

# .tfstate files
*.tfstate
*.tfstate.*

# Crash log files
crash.log
crash.*.log

# Exclude all .tfvars files, which are likely to contain sensitive data, such as
# password, private keys, and other secrets. These should not be part of version 
# control as they are data points which are potentially sensitive and subject 
# to change depending on the environment.
*.tfvars
*.tfvars.json

# Ignore override files as they are usually used to override resources locally and so
# are not checked in
override.tf
override.tf.json
*_override.tf
*_override.tf.json

# Ignore transient lock info files created by terraform apply
.terraform.tfstate.lock.info

# Include override files you do wish to add to version control using negated pattern
# !example_override.tf

# Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
# example: *tfplan*

# Ignore CLI configuration files
.terraformrc
terraform.rc
```

#### Step 3
```
git push -u origin oleh  
```



# If you encounter a branch conflict during a pull request, use these steps:

#### Step 1

```
 git pull origin oleh --allow-unrelated-histories --no-rebase
```

#### Step 2
```
git push 
```

#### Step 3 
```
gh pr create --base main --head oleh --title "Terraform oleh -> main" --body "Creation of Terraform infrastructure for the project"
```