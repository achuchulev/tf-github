# Create GitHub repo with Terraform and test that it exists with kitchen-terraform

### Prerequisites

* terraform
* kitchen
* travis

## Create GitHub repo

### Clone repo and go to the repo directory

```
git clone git@github.com:achuchulev/tf-github.git

cd tf-github/

```

### [Create new GitHub token](https://github.com/settings/tokens) 

### Add token variable in env/gh.env and export it

```

TF_VAR_github_token=your_token

export TF_VAR_github_token

. env/gh.env

```

### Download all required *plugins*

`terraform init`

### Create resources

`terraform apply`

### Destroy resources

`terraform destroy`

## Run test

```
brew install rbenv
rbenv install 2.3.1
rbenv local 2.3.1
rbenv versions
```

add the following lines to your ~/.bash_profile:

```
eval "$(rbenv init -)"
true
export PATH="$HOME/.rbenv/bin:$PATH"
```

run `source ~/.bash_profile` to reload profile

### For MAC

install:

```
gem install bundler
bundle install
```

run test:

`bundle exec kitchen test`
