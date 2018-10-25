# Create GitHub repo with Terraform and test that it exists with kitchen-terraform

### Prerequisites

* terraform
* kitchen
* travis

## Create GitHub repo

#### Clone repo and go to the repo directory

```
git clone git@github.com:achuchulev/tf-github.git

cd tf-github/
```

#### [Create new GitHub token](https://github.com/settings/tokens) 


#### Add token variable in env/gh.env

`TF_VAR_github_token=your_token`

#### Export env var

`export TF_VAR_github_token`

#### Reload env vars

`. env/gh.env`

#### Download all required *plugins*

`terraform init`

#### Create resources

`terraform apply`

#### Destroy resources

`terraform destroy`

## Run test

### on Linux

#### Prerequisites

Install ruby gems

```
sudo gem install test-kitchen
sudo gem install kitchen-terraform
sudo gem install kitchen-inspec
```

#### Run the test

`sudo kitchen test`

### on MAC

#### Prerequisites

##### Install rbenv to use ruby version 2.3.1

```
brew install rbenv
rbenv install 2.3.1
rbenv local 2.3.1
rbenv versions
```

##### Add the following lines to your ~/.bash_profile:

```
eval "$(rbenv init -)"
true
export PATH="$HOME/.rbenv/bin:$PATH"

```

##### Reload profile: 

`source ~/.bash_profile`

##### Install bundler

```
gem install bundler
bundle install
```

#### Run the test

`bundle exec kitchen test`
