# ⚙️Deploying a Static website using Amazon S3
In this Project i'm deploying a static web application  on a Amazon S3 that is ( Amazon Simple Stroage Service) is a highly available, durable object storage service that can also host static websites.
## 🛠️Steps to Deploy
Login to **AWS** console and in _search_ bar search S3 , then open S3 console. 
### Step.1) Create an S3 bucket
* Open the ***AWS S3*** console
* Click on **Create Bucket**
* After clicking Create Bucket we have make some configuration
* Give a name to Bucket (e.g- `aws-s3-staticwebsite-bucket`), *- A name should be Unique because it is Globally available*
* Other configuration kept as it is *We can also change it in `Object Ownership` and `Block public Access` but we can do after adding our data in bucket*
* click on Create Bucket and your bucket is created,
![alt text](<image/Screenshot 2025-06-30 210938.png>)
### Step.2) Upload file & folder of our Website
* After creating Bucket ,Click on that bucket name
* Inside Bucket ,click on ***Upload***
![alt text](<image/Screenshot 2025-06-30 211705.png>)
* After Clicking on Upload their is two option `Add files` & `Add folder` ,we have to separately add files and folder of our webapp.
![alt text](<image/Screenshot 2025-06-30 211935.png>)
* In that page click on `add files` and select the files form our webapp folder and click open to add and then click on `upload` ,we have successfully added our Webapp Files in a S3 Bucket, as given 
![alt text](<image/Screenshot 2025-06-30 211956.png>)
* And now we have to add the folder which has also data of our webapp, so go back to the upload page and click on `add folder` select folder of our webapp and then select open and then scroll down add click on`upload` to add folder in the S3 bucket, as given
![alt text](<image/Screenshot 2025-06-30 212250.png>)

### Step.3) Give Permissios for public access
* Go to the bucket where we can see the Objects which we can added to the Bucket , On that page we can see ***Permission*** option , Click on that
* After clicking we can see some Configuration in that , ` Block Public access` is `on` ,we have to ***Disable*** it for Public acess 
* Click on that `Edit` and ***remove the Blue tick*** and click on `save changes`
![alt text](<image/Screenshot 2025-06-30 212325.png>)
* But after this Configuration we didn`t get public access ,for that we have make some other configuration
### Step.4) Enable ACL
* In below Block Public Access , their is Bucket Policy option , i dont add any policy -( for your other users you can add policy )
* Below that their is  `Object Ownership` in that click on `edit`
* Inside the Edit Object Ownership we have ***Enable Access Control List*** which give public access.
* Click On `ACLs enabled` then,
* Tick the given `I acknowledge that ACLs wiil be restored` then,
* In Object Ownership click on `Bucket owner perferred` -for full control access of owner on bucket and Second is Object writer  in that object writer remains the object owner
* after all configuration CLick on ` save changes  `
 ![alt text](<image/Screenshot 2025-06-30 212451.png>)
 ### Step.5) Make publick using ACL
 * After making object ownership , go to the Bucket
 * Select all the **Objects** which we added to bucket
 * Click on `Actions` then 
 * In actions scroll down and click on `Make public using ACL` then,
 * click on `Make public`
 ![alt text](<image/Screenshot 2025-06-30 212514.png>)
 ### Step.6) Getting End point for access
 * After making public using ACL ,we can access it separately for making one End Point of our webapp we have to enable S3 Static website hosting for that we have do some configuration
 * Go to our bucket in that ,click on `Properties`
 * scroll down, last one is `Static Website Hosting` on that click on `Edit` 
 * After clicking edit we have to make some configuration 
 * Click on `enable` to enable static website hosting 
 * In hosting type , click on `Host a static website ` because we are hosting static website 
 * In index document add file main page/first page , as my page is `index.html`
 * In error document you can add error file ,but - _it is optionL_ we can add or not
 * Redirection rules are also optional 
 * After making all configuration click on `Save changes` 
 * You can get an `End point ` in static website hosting in the properties ![alt text](<image/Screenshot 2025-06-30 212743.png>)
 * copy that End point and hit on browsers and, Here is your WEBAPP on your desktop.

 ![alt text](<image/Screenshot 2025-06-30 212803.png>)
 ![alt text](<image/Screenshot 2025-06-30 212818.png>)
 ![alt text](<image/Screenshot 2025-06-30 212840.png>)
 ## 📄Project Summary 
 This project demonstrates how to deploy a static website using AWS S3. It involves creating an S3 bucket, uploading static files (HTML, CSS), configuring static website hosting, and setting public access enabling ACL which is ACCESS CONTROL LIST, Enable Static Website Hosting For End Point.This approach provides an easy, cost-effective, and highly available solution for hosting static content without needing a web server.