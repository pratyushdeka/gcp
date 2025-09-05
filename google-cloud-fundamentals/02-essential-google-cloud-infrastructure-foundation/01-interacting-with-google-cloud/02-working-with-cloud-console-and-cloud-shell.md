Use Cloud Shell to create a Cloud Storage Bucket
- Open Cloud Shell and ran
	```
	gcloud storage buckets create gs://[BUCKET_NAME] -> BUCKET_NAME: pratyush
	```

Upload a file
- Open Cloud Shell and upload a file
- To copy the uploaded file into the bucket pratyush
	```
	gcloud storage cp [MY_FILE] gs://pratyush
	```

Create a persistent state in Cloud Shell
- The gcloud command often requires you to specify values such as a **Region**, **Zone**, or **Project ID** which may lead to typo
- Set common values in environment variables and use them instead of typing the actual values
	- Identify available regions
		```
		$gcloud compute regions list
		```
	- Create and verify an environment variable
		- Create an environment variable for the region
			```
			INFRACLASS_REGION=[YOUR_REGION]
			```
		- Verify with echo
			```
			echo $INFRACLASS_REGION
			```

Append the environment variable to a file
- Create a subdirectory
	```
	mkdir infraclass
	```
- Create a file called `config` in the infraclass directory:
	```
	touch infraclass/config
	```
- Append the value of your Region environment variable to the `config` file:
	```
	echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config
	```
- Create a second environment variable for your Project ID
```
INFRACLASS_PROJECT_ID=[YOUR_PROJECT_ID]
```
- Append the value of your Project ID environment variable to the `config` file
  ```
  echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config
  ```
- Use the source command to set the environment variables, and use the echo command to verify that the project variable was set
   ```
   source infraclass/config
   echo $INFRACLASS_PROJECT_ID
   ```

Modify the bash profile and create persistence
- Edit the shell profile with the following command
  ```
  nano .profile
  ```
- Add the following line to the end of the file:
	```
  source infraclass/config
  ```
- Save and exit the file