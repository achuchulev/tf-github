# Sample repo with example of github provider usage in terraform and test with kitchen-terraform in travis

### Prerequisits

* terraform
* kitchen
* travis

### Run

* clone repo 

```

git clone git@github.com:achuchulev/tf-github.git

```

* go to repo folder

```

cd tf-github/

```

* [Create new GitHub token](https://github.com/settings/tokens) 

* Add token variable in env/gh.env  

```
TF_VAR_github_token=your_token
export TF_VAR_github_token

```

* export variable 

```

. env/gh.env

```

* Download required *plugins*

```

terraform init

```

* Create resources

```

terraform apply

```

* Destroy resources


```

terraform destroy

```

### Test

* brew install rbenv

* rbenv install 2.3.1

* rbenv local 2.3.1

* rbenv versions

* add the following to your ~/.bash_profile:

```

eval "$(rbenv init -)"
true
export PATH="$HOME/.rbenv/bin:$PATH"
source ~/.bash_profile

```

* gem install bundler

* bundle install

* bundle exec kitchen test
