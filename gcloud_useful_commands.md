## Subjective List of Useful ```gcloud``` Commands


Useful reference with exhaustive list of `gcloud` commands is available [here](https://gist.github.com/pydevops/cffbd3c694d599c6ca18342d3625af97#011-service-account).


#### 1. Log-in via browser

To go to the log-in panel of the default browser run:

```
gcloud auth login
```

To login in via a specific account you can run:

``` 
gcloud auth login my_name@my_domain.ext 
```


Last but not least, in order to log out of all accounts run:

```
gcloud auth revoke --all
```

To log out of specific account run:

```
gcloud auth revoke my_name@my_domain.ext
```



#### 2. Use service account

Suppose you have a service account's JSON file and that the path to this file is ```/path/.../file.JSON```.

In order to activate the service account using this JSON file run:

``` 
gcloud auth activate-service-account --key-file=/path/.../file.JSON
```


#### 3. View all ```gcloud``` accounts, view active account, change active account

In order to display the list of *credentialed* accounts run:

```
gcloud auth list 
```

If you want to check which account is active, run:

```
gcloud config get-value account
```

In order to change the active account run:
``` 
gcloud config set account `ACCOUNT`
```


#### 4. View all available `gcloud` projects, view active project, set active project

In order to display a full list of all available `gcloud` project use the following command:

```
gcloud projects list
```

To display only the active `gcloud` project use the following command:

```
gcloud config get-value project
```

Suppose you want to activate the `MY_PROJECT` Google Cloud project. To do this use:

``` 
gcloud config set project MY_PROJECT
```

Read more on this [here](https://stackoverflow.com/questions/46770900/how-to-change-the-project-in-gcp-using-cli-commands).


#### XYZ. Create & configure a new service account


This section is based on [official `gcloud` documentation](https://cloud.google.com/iam/docs/creating-
managing-service-accounts).

##### XYZ.1. Create a new service account

Assumptions: the IAM API is active for the project for which you want to create the service account.

In order to create a service account use the command:

```
gcloud iam service-accounts create SERVICE_ACCOUNT_ID \
    --description="DESCRIPTION" \
    --display-name="DISPLAY_NAME"
```

For example, if you want to create an account *JohnDoe* for employee John Doe you could use the following command (this is a highly contrived example - single-user dedicated account, but so be it):

```
gcloud iam service-accounts create JohnDoe \ 
	--description="John Doe's service account" \
	--display-name="John Doe"

```

##### XYZ.2. List the existing service accounts

In order to display the list of existing service accounts run the following command:

```
gcloud iam service-accounts list
```


##### XYZ.3. Grant role to a service account

In order to assign an existing role `MY_ROLE` to Google Cloud service account `SERVICE_ACCOUNT_ID` use the command: 

```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:SERVICE_ACCOUNT_ID@PROJECT_ID.iam.gserviceaccount.com" \
    --role="ROLE_NAME" 
```
