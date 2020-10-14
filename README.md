# OAC Snapshot Automation
Automating the process of Creating Snapshots in Oracle Managed - Oracle Analytics Cloud using Python.

This code will create a snapshot using the prefix and timestamp and uploads the file to an Object Storage bucket.

![alt text](https://github.com/prampradeep/OACSnapshotAutomation/blob/main/Images/AutoSnapshot.PNG?raw=true)

## Setup 

After completing all the steps, Run the `CreateSnapshot.py` file which will create the snapshot file and uplaod to the specified Object Storage bucket as per your inputs.

### 1. Chrome Install 

  My code is based on Chrome browser and I'm using Oracle Linux 7 
  
  ```
  # Oracle Linux 7
  sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
  sudo yum -y install redhat-lsb libXScrnSaver
  sudo yum -y localinstall google-chrome-stable_current_x86_64.rpm
  ```
 
 ### 2. OCI and Selenium Packages for Python 
 
  We need to make sure we have the selenium package available.
  
  ```
  pip3 install selenium # For Automating Snapshot Creation
  pip3 install oci  # For uplaod to Object Storage
  ```
  
 ### 3. Clone the Git Repo
 
  Clone the repository to your Server/Machine
  
  ```
  git clone https://github.com/prampradeep/OACSnapshotAutomation
  ```
 
 ### 4. Download chromedriver 
 
 Download the chromedriver which is in line with your chrome version. Make sure to place it inside Cloned repository directory.
 
 ```
 cd OACSnapshotAutomation
 wget https://chromedriver.storage.googleapis.com/85.0.4183.87/chromedriver_linux64.zip
 unzip chromedriver_linux64.zip
 ```
 
 ### 5. Edit Configuration.py
 
 This is the most important part where we provide all the necessary information. Edit the configuration.py file and add information as needed.
 
 ```
  hostname = '< OAC HOST NAME>'
  UserName = '<USERNAME>'
  Password = '<PASSWORD>'
  prefix = '<PREFIX_FOR_FILENAME>'
  SnapPassword = '<SNAPSHOT_PASSWORD>'
  namespace = '<TENANCY NAMESPACE>'
  bucket = '<BUCKET_NAME>'
  
 ```
 
### 6. OCI Config

This is needed for uplaoding Snapshot to Object Storage bucket. make sure to have the `config` file under $HOME/.oci folder.

Sample Config file 
```
[DEFAULT]
user= <USER_OCID>
fingerprint= <FINGERPRINT_API_SIGNING_KEY>
key_file= <PATH_TO_PRIVATE_KEY>
tenancy= <TENANCY_OCID>
region= <REGION>
```

### Contact 
In case of issues while setting this up, you can reach out to me at <rampradeep.pakalapati@gmail.com>

 
