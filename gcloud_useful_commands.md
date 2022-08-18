## Subjective List of Useful ```gcloud``` Commands


Useful reference with exhaustive list of `gcloud` commands is available [here](https://gist.github.com/pydevops/cffbd3c694d599c6ca18342d3625af97#011-service-account).


#### 1. Log-in via browser

``` gcloud auth login ```


#### 2. Log-in using service account

Suppose you have a service account's JSON file and that the path to this file is ```/path/.../file.JSON```.

In order to activate the service account using this JSON file run:

``` 
gcloud auth activate-service-account --key-file=/path/.../file.JSON
```


#### 3. View ```gcloud``` accounts

In order to display the list of *credentialed* accounts run:

```
gcloud auth list 
```


#### 4. Change the active ```gcloud``` account

In order to change the active account run:

``` 
gcloud config set account `ACCOUNT`
```


#### 5. View all available `gcloud` projects

In order to display a full list of all available `gcloud` project use the following command:

```
gcloud projects list
```


#### 6. View the active `gcloud` project

In order to display only the active `gcloud` project use the following command:

```
gcloud config get-value project
```


#### 7. Change the active `gcloud` project

Suppose you want to activate the `MY_PROJECT` Google Cloud project. To do this use:

``` 
gcloud config set project MY_PROJECT
```

Read more on this [here](https://stackoverflow.com/questions/46770900/how-to-change-the-project-in-gcp-using-cli-commands).


#### 8. Create & configure a new service account


This section is based on [official `gcloud` documentation](https://cloud.google.com/iam/docs/creating-
managing-service-accounts).

##### 8.1. Create a new service account

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

##### 8.2. List the existing service accounts

In order to display the list of existing service accounts run the following command:

```
gcloud iam service-accounts list
```


##### 8.3. Grant role to a service account

In order to assign an existing role `MY_ROLE` to Google Cloud service account `SERVICE_ACCOUNT_ID` use the command: 

```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:SERVICE_ACCOUNT_ID@PROJECT_ID.iam.gserviceaccount.com" \
    --role="ROLE_NAME" 
```


