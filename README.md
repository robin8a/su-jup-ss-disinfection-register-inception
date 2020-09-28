# su-jup-ss-disinfection-register-inception

# Starting React App
```sh
source ~/.bash_profile
npx create-react-app su-jup-ss-disinfection-register
```

# Git

```sh
git remote add origin https://github.com/Summus-App-Group/su-ss-disinfection-register.git
git push -u origin master
```


# To user aws commands
## Use this commands with the 3.7 update
```sh
export PATH=~/Library/Python/3.7/bin:$PATH
source ~/.bash_profile

```


# AWS amplify

## Init
```sh
amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project sussdisinfectionregi
? Enter a name for the environment disregapi
? Choose your default editor: Visual Studio Code
? Choose the type of app that you're building javascript
Please tell us about your project
? What javascript framework are you using react
? Source Directory Path:  src
? Distribution Directory Path: build
? Build Command:  npm run-script build
? Start Command: npm run-script start
```

## API

```sh

amplify add api
? Please select from one of the below mentioned services: GraphQL
? Provide API name: sussdisinfectionregi
? Choose the default authorization type for the API Amazon Cognito User Pool
Using service: Cognito, provided by: awscloudformation
 
 The current configured provider is Amazon Cognito. 
 
 Do you want to use the default authentication and security configuration? Default configuration
 Warning: you will not be able to edit these selections. 
 How do you want users to be able to sign in? Email
 Do you want to configure advanced settings? No, I am done.
Successfully added auth resource
? Do you want to configure advanced settings for the GraphQL API Yes, I want to make some additional changes.
? Configure additional auth types? No
? Configure conflict detection? No
? Do you have an annotated GraphQL schema? No
? Do you want a guided schema creation? Yes
? What best describes your project: Single object with fields (e.g., “Todo” with ID, name, description)
? Do you want to edit the schema now? Yes
Please edit the file in your editor: /Users/robin8a/Documents/react_ws/su-ss-disinfection-register/amplify/backend/api/sussdisinfectionregi/schema.graphql
? Press enter to continue 

The following types do not have '@auth' enabled. Consider using @auth with @model
         - Register
Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 

Failed compiling GraphQL schema:
Unknown type "DateTime". Did you mean "AWSTime" or "AWSDateTime"?
? Correct the errors in schema.graphql and press Enter to re-compile.

Path to schema.graphql:
/Users/robin8a/Documents/react_ws/su-ss-disinfection-register/amplify/backend/api/sussdisinfectionregi/schema.graphql 

The following types do not have '@auth' enabled. Consider using @auth with @model
         - Register
Learn more about @auth here: https://aws-amplify.github.io/docs/cli-toolchain/graphql#auth 


GraphQL schema compiled successfully.

Edit your schema at /Users/robin8a/Documents/react_ws/su-ss-disinfection-register/amplify/backend/api/sussdisinfectionregi/schema.graphql or place .graphql files in a directory at /Users/robin8a/Documents/react_ws/su-ss-disinfection-register/amplify/backend/api/sussdisinfectionregi/schema
Successfully added resource sussdisinfectionregi locally

Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

```


```sh
amplify push

# Api link
https://fup5pp2ckbdybkocksz3bgj2s4.appsync-api.us-east-1.amazonaws.com/graphql

```

# Installing aws-amplify and aws-amplify-react and configure

```sh
npm install aws-amplify aws-amplify-react
```

## Adding amplify modules
- src/index.js
```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

// AWS amplify modules
import Amplify from 'aws-amplify';
import aws_exports from './aws-exports'

Amplify.configure(aws_exports);

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

```

# Update GraphQL Schema
amplify/backend/api/sussdisinfectionregi/schema.graphql

added: regCreatedAt: String!
```graphql
type Register @model{ 
   id: ID!
   regCedula: String!
   regPrimerNombre: String!
   regSegundoNombre: String!
   regPrimerApellido: String!
   regSegundoApellido: String!
   regFechaNacimiento: AWSDateTime!
   regCelularConductor: String!
   regVehPlaca: String!
   regVehSOAT: String!
   regVehRTM: String!
   regVehSeguros: String!
   regVehNombrePropietario: String!
   regVehTelefonoPropietario: String!
   regVehMailPropietario: String!
   regCreatedAt: String!  
}
```
# update
```sh
amplify push
```

# Adding auth

```sh
amplify add auth
# When I run api I selected Auth
# Auth has already been added to this project. To update run amplify update auth. 


```

# Git use an old commit


```
git checkout <old-commit>
git branch temp-branch
git checkout master
git merge temp-branch
git push origin master

```


# Installing react icons

```sh
# ref: https://react-icons.github.io/react-icons/
npm install react-icons --save

```


https://codyhouse.co/demo-templates/mercurio/index.html


# Publish

- [aws amplify - Hosting](https://docs.amplify.aws/cli/hosting#type-of-deployments)

## amplify add hosting
```sh
amplify add hosting
? Select the plugin module to execute Amazon CloudFront and S3
? Select the environment setup: PROD (S3 with CloudFront using HTTPS)
? hosting bucket name sussdisinfectionregi-20200601075854-hostingbucket
Static webhosting is disabled for the hosting bucket when CloudFront Distribution is enabled.

You can now publish your app using the following command:
Command: amplify publish
```

## amplify publish

```sh

amplify publish
✔ Successfully pulled backend environment disregapi from the cloud.

Current Environment: disregapi

| Category | Resource name                | Operation | Provider plugin   |
| -------- | ---------------------------- | --------- | ----------------- |
| Hosting  | S3AndCloudFront              | Create    | awscloudformation |
| Auth     | sussdisinfectionregi351b5d00 | No Change | awscloudformation |
| Api      | sussdisinfectionregi         | No Change | awscloudformation |
? Are you sure you want to continue? Yes
⠧ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-sussdisinfectionregi-disregapi-164510 AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:21 GMT-0500 (Colombia Standard Time) User Initiated
⠼ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE    authsussdisinfectionregi351b5d00 AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:32 GMT-0500 (Colombia Standard Time)                            
CREATE_IN_PROGRESS hostingS3AndCloudFront           AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:32 GMT-0500 (Colombia Standard Time) Resource creation Initiated
UPDATE_IN_PROGRESS authsussdisinfectionregi351b5d00 AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:31 GMT-0500 (Colombia Standard Time)                            
CREATE_IN_PROGRESS hostingS3AndCloudFront           AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:31 GMT-0500 (Colombia Standard Time)                            
⠋ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS amplify-sussdisinfectionregi-disregapi-164510-hostingS3AndCloudFront-NMOR041L0Q70 AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:32 GMT-0500 (Colombia Standard Time) User Initiated
⠦ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS apisussdisinfectionregi AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:34 GMT-0500 (Colombia Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS S3Bucket             AWS::S3::Bucket                                 Mon Jun 01 2020 08:00:37 GMT-0500 (Colombia Standard Time) 
CREATE_IN_PROGRESS OriginAccessIdentity AWS::CloudFront::CloudFrontOriginAccessIdentity Mon Jun 01 2020 08:00:37 GMT-0500 (Colombia Standard Time) 
⠼ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-sussdisinfectionregi-disregapi-164510-apisussdisinfectionregi-V0OXKU1ZS90B AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:35 GMT-0500 (Colombia Standard Time) User Initiated
⠧ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS S3Bucket AWS::S3::Bucket Mon Jun 01 2020 08:00:39 GMT-0500 (Colombia Standard Time) Resource creation Initiated
⠹ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE    OriginAccessIdentity AWS::CloudFront::CloudFrontOriginAccessIdentity Mon Jun 01 2020 08:00:40 GMT-0500 (Colombia Standard Time)                            
CREATE_IN_PROGRESS OriginAccessIdentity AWS::CloudFront::CloudFrontOriginAccessIdentity Mon Jun 01 2020 08:00:39 GMT-0500 (Colombia Standard Time) Resource creation Initiated
⠼ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE    Register AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:42 GMT-0500 (Colombia Standard Time) 
UPDATE_IN_PROGRESS Register AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:41 GMT-0500 (Colombia Standard Time) 
⠙ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE    CustomResourcesjson AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:46 GMT-0500 (Colombia Standard Time) 
UPDATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:45 GMT-0500 (Colombia Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-sussdisinfectionregi-disregapi-164510-apisussdisinfectionregi-V0OXKU1ZS90B AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:49 GMT-0500 (Colombia Standard Time) 
⠸ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE apisussdisinfectionregi AWS::CloudFormation::Stack Mon Jun 01 2020 08:00:57 GMT-0500 (Colombia Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE S3Bucket AWS::S3::Bucket Mon Jun 01 2020 08:01:13 GMT-0500 (Colombia Standard Time) 
⠙ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE    PrivateBucketPolicy    AWS::S3::BucketPolicy         Mon Jun 01 2020 08:01:16 GMT-0500 (Colombia Standard Time)                            
CREATE_IN_PROGRESS PrivateBucketPolicy    AWS::S3::BucketPolicy         Mon Jun 01 2020 08:01:16 GMT-0500 (Colombia Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS CloudFrontDistribution AWS::CloudFront::Distribution Mon Jun 01 2020 08:01:15 GMT-0500 (Colombia Standard Time)                            
CREATE_IN_PROGRESS PrivateBucketPolicy    AWS::S3::BucketPolicy         Mon Jun 01 2020 08:01:15 GMT-0500 (Colombia Standard Time)                            
⠴ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS CloudFrontDistribution AWS::CloudFront::Distribution Mon Jun 01 2020 08:01:19 GMT-0500 (Colombia Standard Time) Resource creation Initiated
⠸ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE CloudFrontDistribution AWS::CloudFront::Distribution Mon Jun 01 2020 08:05:46 GMT-0500 (Colombia Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE amplify-sussdisinfectionregi-disregapi-164510-hostingS3AndCloudFront-NMOR041L0Q70 AWS::CloudFormation::Stack Mon Jun 01 2020 08:05:49 GMT-0500 (Colombia Standard Time) 
⠏ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-sussdisinfectionregi-disregapi-164510 AWS::CloudFormation::Stack Mon Jun 01 2020 08:06:31 GMT-0500 (Colombia Standard Time) 
CREATE_COMPLETE                     hostingS3AndCloudFront                        AWS::CloudFormation::Stack Mon Jun 01 2020 08:06:28 GMT-0500 (Colombia Standard Time) 
⠴ Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE amplify-sussdisinfectionregi-disregapi-164510 AWS::CloudFormation::Stack Mon Jun 01 2020 08:06:45 GMT-0500 (Colombia Standard Time) 
UPDATE_COMPLETE authsussdisinfectionregi351b5d00              AWS::CloudFormation::Stack Mon Jun 01 2020 08:06:45 GMT-0500 (Colombia Standard Time) 
UPDATE_COMPLETE apisussdisinfectionregi                       AWS::CloudFormation::Stack Mon Jun 01 2020 08:06:44 GMT-0500 (Colombia Standard Time) 
✔ All resources are updated in the cloud

Hosting endpoint: https://dnnn3f3cxsg2t.cloudfront.net


> su-ss-disinfection-register@0.1.0 build /Users/robin8a/Documents/react_ws/su-ss-disinfection-register
> react-scripts build

Creating an optimized production build...
Compiled with warnings.

./src/components/CreateRegister.js
  Line 2:33:  'Auth' is defined but never used  no-unused-vars

Search for the keywords to learn more about each warning.
To ignore, add // eslint-disable-next-line to the line before.

File sizes after gzip:

  168.72 KB  build/static/js/2.da8ab5d0.chunk.js
  2.63 KB    build/static/js/main.aa2d9c7e.chunk.js
  1.12 KB    build/static/css/main.a048f3d1.chunk.css
  787 B      build/static/js/runtime-main.114d56f4.js

The project was built assuming it is hosted at /.
You can control this with the homepage field in your package.json.

The build folder is ready to be deployed.
You may serve it with a static server:

  npm install -g serve
  serve -s build

Find out more about deployment here:

  bit.ly/CRA-deploy

frontend build command exited with code 0
Publish started for S3AndCloudFront
✔ Uploaded files successfully.
Your app is published successfully.
https://dnnn3f3cxsg2t.cloudfront.net

```

# Amplify Storage

```sh
amplify add storage
? Please select from one of the below mentioned services: Content (Images, audio, vi
deo, etc.)
? Please provide a friendly name for your resource that will be used to label this c
ategory in the project: s3ad71f587
? Please provide bucket name: sujupssdisinfectionr31fe549608064783a8cfad0a51a
? Who should have access: Auth users only
? What kind of access do you want for Authenticated users? create/update, read
? Do you want to add a Lambda Trigger for your S3 Bucket? No
Successfully added resource s3ad71f587 locally

amplify push
```



# Empty a bucket: Using the AWS CLI

You can empty a bucket using the AWS CLI only if the bucket does not have versioning enabled. If your bucket does not have versioning enabled, you can use the rm (remove) AWS CLI command with the --recursive parameter to empty a bucket (or remove a subset of objects with a specific key name prefix).

The following rm command removes objects with key name prefix doc, for example, doc/doc1 and doc/doc2.

```sh
aws s3 rm s3://bucket-name/doc --recursive
Use the following command to remove all objects without specifying a prefix.

aws s3 rm s3://bucket-name --recursive

aws s3 ls


aws s3 rm s3://sussdisinfectionregif5783b50c3ef4289a0ccd4fc856164510-disregapi/public --recursive
```

# BarCode reader Cast

```sh
CreateRegister.js:61 not empty position:  0  -  00C21226096
CreateRegister.js:61 not empty position:  4  -  FALLA
CreateRegister.js:61 not empty position:  22  -  BAHAMON
CreateRegister.js:61 not empty position:  38  -  NELLY
CreateRegister.js:61 not empty position:  79  -  CLL
CreateRegister.js:61 not empty position:  80  -  88A
CreateRegister.js:61 not empty position:  81  -  #
CreateRegister.js:61 not empty position:  82  -  30-50
CreateRegister.js:61 not empty position:  107  -  6104141
CreateRegister.js:61 not empty position:  110  -  1100100002
CreateRegister.js:61 not empty position:  270  -  02
CreateRegister.js:61 not empty position:  430  -  10215730
CreateRegister.js:61 not empty position:  436  -  00B100N2111201221112022```
```

# Push Commits to an Additional Git Repository
- [*** Works *** Push Commits to an Additional Git Repository](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-mirror-repo-pushes.html)

```sh

git remote -v
origin  https://github.com/Summus-App-Group/su-ss-disinfection-register.git (fetch)
origin  https://github.com/Summus-App-Group/su-ss-disinfection-register.git (push)

git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/su-ss-disinfection-register

git remote set-url --add --push origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/su-ss-disinfection-register
git remote set-url --add --push origin https://github.com/Summus-App-Group/su-ss-disinfection-register.git

```

# Changing/Adding and use remotes url

- https://help.github.com/en/github/using-git/changing-a-remotes-url
- https://git-scm.com/docs/git-remote
- https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes

```sh
git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <name> <url>

git remote add aws-code-commit https://git-codecommit.us-east-1.amazonaws.com/v1/repos/su-ss-disinfection-register

git remote -v

clear
git remote add aws-code-commit https://git-codecommit.us-east-1.amazonaws.com/v1/repos/su-ss-disinfection-register
git remote -v
git pull aws-code-commit master
git log


```

# amplify add hosting

```sh
amplify add hosting
? Select the plugin module to execute Hosting with Amplify Console (Managed hosting with custom domains, Continuous deployment)
? Choose a type Continuous deployment (Git-based deployments)
? Continuous deployment is configured in the Amplify Console. Please hit enter once you connect your repository 
Amplify hosting urls: 
┌──────────────┬──────────────────────────────────────────────┐
│ FrontEnd Env │ Domain                                       │
├──────────────┼──────────────────────────────────────────────┤
│ master       │ https://master.d1zht4s4hs3p93.amplifyapp.com │
└──────────────┴──────────────────────────────────────────────┘

```

# Amplify dashboard CICD

https://us-east-1.console.aws.amazon.com/amplify/


# Barcode Scanner + Screen Input (toggle)
- [*** works *** Keyboard ReactNative](https://reactnative.dev/docs/keyboard)
- [Dismiss the Keyboard in React Native from Anywhere](https://www.youtube.com/watch?v=z_FVCeWloig)
- https://github.com/facebook/react-native/issues/14045
- https://stackoverflow.com/questions/38958272/disable-keyboard-with-html-input-and-allow-scanners
- https://laracasts.com/discuss/channels/general-discussion/detect-barcode-scanner-javascript
- https://www.thepolyglotdeveloper.com/2015/10/implement-a-barcode-scanner-using-react-native/
- https://stackoverflow.com/questions/54843886/module-not-found-cant-resolve-react-native
- https://reactjs.org/docs/accessibility.html
- https://medium.com/@akshay.s.somkuwar/dismiss-hide-keyboard-on-tap-outside-of-textinput-react-native-b94016f35ff0


```sh
npm install react-native-web

```


# React 
- [How to Build Web Barcode Apps with React and WebAssembly](https://www.dynamsoft.com/codepool/build-web-barcode-apps-react-wasm.html)
- [*** works *** npm: react-barcode-reader](https://www.npmjs.com/package/react-barcode-reader)
- https://medium.com/@yushulx/how-to-build-web-barcode-scanner-using-react-and-webcam-d36ba26bddfd
- https://github.com/yushulx/javascript-barcode/tree/master/examples/react-wasm-barcode/src
- [React Native QR Code Scanner Tutorial](https://www.youtube.com/watch?v=e7qf9UJvoC0)
- https://medium.com/@dinukadilshanfernando/implementing-a-barcode-scanner-by-using-react-native-camera-b170de4b7f51

# React Routing
- [*** Works *** React Router Tutorial | React For Beginners](https://www.youtube.com/watch?v=Law7wfdg_ls)
- [ReactJS Basics - #15 React Router - Route Setup](https://www.youtube.com/watch?v=eofpZPRUnP8)


```sh
# npm uninstall --save react-router
npm install --save react-router-dom

```


# Show table and Export to csv
- [*** Works *** An easy way to create a customize dynamic table in react js](https://dev.to/abdulbasit313/an-easy-way-to-create-a-customize-dynamic-table-in-react-js-3igg)
- [*** Works *** Export csv](https://www.npmjs.com/package/export-to-csv)
- https://medium.com/@diego.f.rodriguezh/direct-image-upload-to-aws-s3-with-react-and-express-2f063bc15430
- https://medium.marqeta.com/pre-signing-aws-s3-urls-136f203a75cd
- [*** Works *** Amplify Storage Upload, Download, Signed URL ](https://docs.amplify.aws/lib/storage/getting-started/q/platform/js#manual-setup-import-storage-bucket)

## External link

- [*** works *** npm: External Link](https://www.npmjs.com/package/react-external-link)


## Display buttons in map

- [Dynamically render multiple buttons in react js from an array](https://www.freecodecamp.org/forum/t/dynamically-render-multiple-buttons-in-react-js-from-an-array/259666)


## ReactJS Modal

- [Modal](https://react-bootstrap.github.io/components/modal/)

# Table 
https://www.npmjs.com/package/rc-table
https://freefrontend.com/css-tables/

## Filters
https://medium.com/open-graphql/implementing-search-in-graphql-11d5f71f179
https://docs.aws.amazon.com/appsync/latest/devguide/quickstart-write-queries.html
https://docs.aws.amazon.com/appsync/latest/devguide/designing-your-schema.html
https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Query.html
https://www.youtube.com/watch?v=SxwMHqRUrBk

## AppSync
### Credentials
https://master.d2b4ekdzzxc4fg.amplifyapp.com/
sussdi351b5d00_app_clientWeb
ClientId: 5uk4ov2ifhnhj9o5rkchlee82u
Username: javigomez@yopmail.com
Password: 4dm1n2020$$


```js

query listRegisters {
  listRegisters {
    items {
      id
      regCedula
    }
  }
}

query listRegistersByCedula {
  listRegisters(
    filter:{
      regCedula: {
        contains: "6776748"
    }
  }) {
    items {
      id
      regCedula
    }
  }
}


query listRegistersByDates {
  listRegisters(filter:{
    regCreatedAt: {
      between: ["2020-06-23T00:00:00", "2020-06-24T00:00:00"]
    }
  }) {
    items {
      id
      regCedula
      regCreatedAt
    }
  }
}

query GetRegisterById {
  getRegister(id: "0e0e0392-5f6e-4221-940a-cf33b6eb445d") {
    id
    regCedula
  }
}


query listRegisterByDate {
  registersByDate(
    filter: { 
        regCreatedAt: {
            between: ["2020-06-23T00:00:00", "2020-06-24T00:00:00"]
        }
    }
  ){
    items {
      id
      regCedula
      regCreatedAt
    }
  }
}

query ListOrdersForCustomerIn2019 {
  registersByDate(regCreatedAt: { beginsWith: "2019" }) {
    items {
      id
    }
  }
}


query listRegisterByDate {
  listRegisters(
    filter: { 
        regEpoch: {
            between: [1593752400, 1593838800]
      }
    }
  ){
    items {
      id
      regCedula
      regCreatedAt
    }
  }
}


query listRegisterByDate {
  listRegisters(
    filter: { 
      regEpoch: {
        between: [1593752400,1593838800]
    	}
    },
    limit: 100000
  ){
    items {
      regCedula
      regEpoch
    }
  }
}


query listRegitersBeginWith {
  listRegisters(
    filter: {
    	regCreatedAt: { beginsWith: "2020-07-03" }
    }){
    items {
      id
    }
  }
}

query listRegisterByDate {
  listRegisters(limit: 100) {
    items {
      id
    }
  }
}


query listRegisterByDate {
  listRegisters(
    limit: 3000,
    filter: { regEpoch: {gt: 0}}
  ) {
    items {
      id
    }
  }
}

query listRegisterByDate {
  listRegisters(
    limit: 3000,
    filter: { 
      regEpoch: {gt: 1593752400 lt: 1593838800}
    }
  ) {
    items {
      id
    }
  }
}

query ListOrdersForCustomerIn2019 {
  listRegisters(
    limit: 10000
    filter: {
      regCreatedAt: { beginsWith: "2020-07-03" }
    }) {
    items {
      id
    }
  }
}


query ListLocationParent {
  listLocations(
    limit: 10
  )  
  {
    items {
      title
    }
  }
}


query ListLocationParent {
  listLocations(
    limit: 10
    filter: {
      id: { eq: "f54bc2c2-8e69-41ec-afbc-0dae235abe3a"}
    }
  )  
  {
    items {
      title
      location {
        title
      }
      locations {
        items{
          title
        }
      }
    }
  }
}


query ListOrdersForCustomerIn2019 {
  listRegisters(
    limit: 99999
    filter: {
      regEpoch: { gt: 1594771200, lt: 1594857600 }
    }) {
    items {
      id
    }
  }
}

```


# Update videoSrc

- [*** works ***](https://reactjs.org/docs/react-component.html#componentdidupdate)

```js
componentDidUpdate(prevProps) {
  // Typical usage (don't forget to compare props):
  console.log("# componentDidUpdate")
  if (this.props.homeLink !== prevProps.homeLink) {
    console.log("# componentDidUpdate this.props.homeLink !== prevProps.homeLink")
    // this.fetchData(this.props.homeLink);
    this.setState({ regVideoSrc: this.props.homeLink})
  }
}

```
# Group by 
https://stackoverflow.com/questions/29364262/how-to-group-by-and-sum-array-of-object




# Backup videos
- [AWS tutorial: Download an Entire S3 bucket with one command using the AWS CLI](https://www.youtube.com/watch?v=PJ_nwPWKgW8)


# Queries
https://dev.to/johanneskonings/aws-amplify-api-graphql-queries-49b

# Build a real-life serverless app with AWS Amplify
https://medium.com/faun/build-a-real-life-serverless-app-with-aws-amplify-c78fa266ee08
- [Going serverless with React and AWS Amplify Part 2: Creating And Using Serverless Services](https://www.freecodecamp.org/news/going-serverless-with-react-and-aws-amplify-part-2-creating-and-using-serverless-services-d401ba346eeb/)
- https://github.com/aws-amplify/amplify-js/issues/2463


# Export Dynamo to CSV

https://stackoverflow.com/questions/33357821/how-to-export-a-dynamodb-table-as-a-csv-through-aws-cli-without-using-pipeline/33358747
https://medium.com/@quodlibet_be/an-overview-of-tools-to-export-from-dynamoddb-to-csv-d2707ad992ac

```sh

export PATH=~/Library/Python/3.6/bin:$PATH

source ~/.bash_profile

sudo nano ~/.bash_profile

## Copy-Paste following lines

# Add AWS CLI

export PATH=~/Library/Python/3.8/bin:$PATH

aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[id.S,regCedula.S,regPrimerNombre.S,regSegundoNombre.S,regPrimerApellido.S,regSegundoApellido.S,regFechaNacimiento.S,regCelularConductor.S,regVehPlaca.S,regVehSOA.ST,regVehRTM.S,regVehSeguros.S,regVehNombrePropietario.S,regVehTelefonoPropietario.S,regVehMailPropietario.S,regCreatedAt.S,regOwnerId.S,regVideoSrc.S,regLocatio.Sn,regIsAcceptedTerms.S,regOwnerUsername.S,regVehPropCedula.S,key.S,qty.S,regVehEmpresa.S,regVehSOATCompany.S,regVehRTMCompany.S,regVehSegurosCompany.S]" \
    --output text > dataDump.csv

regCedula,regPrimerNombre,regSegundoNombre,regPrimerApellido,regSegundoApellido,regFechaNacimiento,regCelularConductor,regVehPlaca,regVehSOAT,regVehRTM,regVehSeguros,regVehNombrePropietario,regVehTelefonoPropietario,regVehMailPropietario,regCreatedAt,regOwnerId,regVideoSrc,regLocation,regIsAcceptedTerms,regOwnerUsername,regVehPropCedula,key,qty,regVehEmpresa,regVehSOATCompany,regVehRTMCompany,regVehSegurosCompany

aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[id.S,regCedula.S]" \
    --output text > dataDumpo.csv


aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[regCedula.S, regVehPlaca.S, regVehSOAT.S, regVehSeguros.S, regVehNombrePropietario.S, regVehTelefonoPropietario.S,regVehMailPropietario.S, regCreatedAt.S,regOwnerId.S, regVideoSrc.S, regLocation.S, regIsAcceptedTerms.S, regOwnerUsername.S, regVehPropCedula.S,regVehEmpresa.S, regVehSOATCompany.S, regVehRTMCompany.S, regVehSegurosCompany.S]" \
    --output text > dataDump.csv

Header
regCedula	 regVehPlaca	regVehSOAT	regVehSeguros	regVehNombrePropietario	regVehTelefonoPropietario	regVehMailPropietario	regCreatedAt	regOwnerId	regVideoSrc	regLocation	regIsAcceptedTerms	regOwnerUsername	regVehPropCedula	regVehEmpresa	regVehSOATCompany	regVehRTMCompany	regVehSegurosCompany


aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[createdAt.S, regCedula.S, regVehSOAT.S, regVehSeguros.S, regLocation.S, regIsAcceptedTerms.S, regVehEmpresa.S, regVehSOATCompany.S, regVehRTMCompany.S, regVehSegurosCompany.S]" \
    --output text > dataDump_290720_0932.csv


createdAt.S	regCedula.S	regVehSOAT.S	regVehSeguros.S	regLocation.S	regIsAcceptedTerms.S	regVehEmpresa.S	regVehSOATCompany.S	regVehRTMCompany.S	regVehSegurosCompany.S


```
## Upload Quick Sight manifest and dataDump

https://docs.aws.amazon.com/quicksight/latest/user/supported-manifest-file-format.html
https://docs.aws.amazon.com/cli/latest/reference/s3/cp.html
https://github.com/awsdocs/amazon-quicksight-user-guide/blob/master/doc_source/supported-manifest-file-format.md
https://www.youtube.com/watch?v=teyfv9r_d6c

```sh
cd quicksight/
export PATH=~/Library/Python/3.8/bin:$PATH

aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[createdAt.S, regCedula.S, regVehSOAT.S, regVehSeguros.S, regLocation.S, regIsAcceptedTerms.S, regVehEmpresa.S, regVehSOATCompany.S, regVehRTMCompany.S, regVehSegurosCompany.S]" \
    --output text > RegistersDataDump.tsv

# Add header to the file
createdAt.S	regCedula.S	regVehSOAT.S	regVehSeguros.S	regLocation.S	regIsAcceptedTerms.S	regVehEmpresa.S	regVehSOATCompany.S	regVehRTMCompany.S	regVehSegurosCompany.S

# Upload the files to S3

# aws s3 cp RegistersDataDump.tsv s3://registers.dynamodb.backup/RegistersDataDump.tsv --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers full=uri=79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be

# aws s3 cp registersmanifest.json s3://registers.dynamodb.backup/registersmanifest.json --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers full=uri=79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be

aws s3 cp RegistersDataDump.tsv s3://registers.dynamodb.backup/RegistersDataDump.tsv
aws s3 cp registersmanifest.json s3://registers.dynamodb.backup/registersmanifest.json

```


## Free Registers Dump

```sh
aws dynamodb scan \
    --table-name FreeRegister-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[createdAt.S, frVehPhotoSrc.S, frVehTag.S]" \
    --output text > FreeRegistersDataDump.tsv


aws s3 cp FreeRegistersDataDump.tsv s3://registers.dynamodb.backup/FreeRegistersDataDump.tsv
aws s3 cp freeregistersmanifest.json s3://registers.dynamodb.backup/freeregistersmanifest.json

### Tap Header
createdAt.S	frVehPhotoSrc.S	frVehTag.S


```

```json
{
  "__typename": "FreeRegister",
  "createdAt": "2020-07-29T08:48:15-05:00",
  "frVehPhotoSrc": "20200729_084756.jpg",
  "frVehTag": "VFE713",
  "id": "1cb894aa-f27b-4bb0-bd11-3025da2ac714",
  "updatedAt": "2020-07-29T13:48:11.212Z"
}
```


# Dynamo Update

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.UpdateExpressions.html

```js

Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi

aws dynamodb update-item \
    --table-name ProductCatalog \
    --key '{"Id":{"N":"789"}}' \
    --update-expression "SET ProductCategory = :c, Price = :p" \
    --expression-attribute-values file://values.json \
    --return-values ALL_NEW  

```
# react capture a photo
https://www.npmjs.com/package/react-html5-camera-photo
https://stackoverflow.com/questions/39062595/how-can-i-create-a-png-blob-from-binary-data-in-a-typed-array
https://javascript.info/blob
https://stackoverflow.com/questions/21887882/extract-an-image-blob-from-database-and-insert-it-in-a-frame-java
https://gist.github.com/candycode/f18ae1767b2b0aba568e
https://developer.mozilla.org/en-US/docs/Web/API/Blob

```js
var data = new Uint8Array([
  137,80,78,71,13,10,26,10,0,0,0,13,73,72,68,82,0,0,0,8,0,0,
  0,8,8,2,0,0,0,75,109,41,220,0,0,0,34,73,68,65,84,8,215,99,120,
  173,168,135,21,49,0,241,255,15,90,104,8,33,129,83,7,97,163,136,
  214,129,93,2,43,2,0,181,31,90,179,225,252,176,37,0,0,0,0,73,69,
  78,68,174,66,96,130]);
var blob = new Blob([data], { type: "image/png" });
var url = URL.createObjectURL(blob);
var img = new Image();
img.src = url;
console.log("data length: " + data.length);
console.log("url: " + url);
document.body.appendChild(img);
img { width: 100px; height: 100px; image-rendering: pixelated; }
```
# Queries
https://docs.amplify.aws/cli/graphql-transformer/directives#how-to-use-key
https://docs.amplify.aws/cli/graphql-transformer/overview#create-a-graphql-api
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html#Query.KeyConditionExpressions
https://egghead.io/lessons/aws-execute-queries-within-the-aws-appsync-console



# Tag OCR Detection

https://docs.aws.amazon.com/rekognition/latest/dg/text-detecting-text-procedure.html

```sh
aws rekognition detect-text \
--image "S3Object={Bucket=bucketname,Name=input.jpg}" 

```


# Amplify Rekongnition with predictions
https://docs.amplify.aws/lib/predictions/identify-text/q/platform/js#identify-plain-text
- [*** works ***](https://medium.com/faun/using-aws-amplify-to-develop-full-stack-react-app-part-2-integrate-amazon-ml-services-283dadc0f5d8)
https://undefobj.github.io/docs/js/predictions
https://docs.amplify.aws/lib/predictions/identify-text/q/platform/ios#set-up-the-backend
https://docs.amplify.aws/lib/predictions/getting-started/q/platform/ios
https://aws.amazon.com/es/blogs/mobile/announcing-the-new-predictions-category-in-amplify-framework/
https://github.com/aws-amplify/amplify-js/issues/1150
https://amplify-workshop.go-aws.com/110_ai/10_rekognition.html
https://medium.com/@gerard.sans/tutorial-creating-findkeanu-app-using-new-amplify-predictions-and-angular-92699572916
https://medium.com/faun/using-aws-amplify-to-develop-full-stack-react-app-part-2-integrate-amazon-ml-services-283dadc0f5d8
https://undefobj.github.io/docs/js/predictions
https://dev.to/rpostulart/the-guide-to-add-ai-to-your-react-native-app-with-aws-amplify-4c6a

```sh

amplify add predictions


The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
192:su-ss-disinfection-register robin8a$ amplify add predictions
? Please select from one of the categories below Identify
? What would you like to identify? Identify Text
? Provide a friendly name for your resource identifyTextfbed195e
? Would you also like to identify documents? Yes
? Who should have access? Auth users only
Successfully added resource identifyTextfbed195e locally

Some next steps:
"amplify push" builds all of your local backend resources and provisions them in the cloud
"amplify publish" builds all of your local backend and front-end resources (if you added hosting category) and provisions them in the cloud

```

## Uploading file to test predictions

```sh
aws s3 cp test.txt s3://mybucket/test2.txt

aws s3 cp vehiculo_placa.jpg s3://sussdisinfectionregif5783b50c3ef4289a0ccd4fc856164510-disregapi/public/vehiculo_placa.jpg

aws s3 ls s3://sussdisinfectionregif5783b50c3ef4289a0ccd4fc856164510-disregapi/public/

https://sussdisinfectionregif5783b50c3ef4289a0ccd4fc856164510-disregapi.s3.amazonaws.com/public/1591358560698.webm


aws s3 cp vehiculo_placa.jpg s3://com.labshutter.images/vehiculo_placa.jpg




```

```sh
aws rekognition detect-text \
--image "S3Object={Bucket=com.labshutter.images,Name=vehiculo_placa.jpg}"

```


# Query Dates

https://janhesters.com/sorting-queries-with-aws-amplifys-key-directive/
https://medium.com/open-graphql/top-9-aws-appsync-features-you-didnt-know-about-57224075ffb1


# Modifying Data in a Table
https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/SQLtoNoSQL.UpdateData.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.UpdateExpressions.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStarted.NodeJs.03.html

## String Date to epoch

https://stackoverflow.com/questions/13707333/javascript-convert-date-time-string-to-epoch/13707414

```js
var epoch = moment(str).unix();
```

## DynamoDB scan regEpoch between
2020-07-07T12:11:24-05:00
GMT: Tuesday, 7 July 2020 5:11:24 PM

1593570000
Wednesday, July 1, 2020 2:20:00 AM

1595726007
Sunday, July 26, 2020 1:13:33 AM
Viewing 1401 to 1481 items
 
## React bacht updatede
Updated with React bash: Viewing 1401 to 1483 items


## AppSync GraphQL query with nextToken
- [*** works *** Build your own multi-user photo album app with React, GraphQL, and AWS Amplify](https://read.acloud.guru/build-your-own-multi-user-photo-album-app-with-react-graphql-and-aws-amplify-bcaeba942159)
https://dev.to/onlybakam/implementing-pagination-with-aws-appsync-5d08


NUMERO DE REGISTROS: Viewing 2901 to 2962 items

NUMERO DE REGISTROS ACTUALIZADOS EPOCH: Viewing 1901 to 1998 items
NUMERO DE REGISTROS ACTUALIZADOS EPOCH: Viewing 2901 to 2959 items


### Amplify DynamoDB scan
- byCustomerByDate https://docs.amplify.aws/cli/graphql-transformer/dataaccess
https://docs.amplify.aws/
https://docs.amplify.aws/cli/graphql-transformer/examples#blog-queries
https://medium.com/@jan.hesters/query-more-items-using-scans-in-aws-amplify-921f50014d43
https://docs.aws.amazon.com/appsync/latest/devguide/using-your-api.html#relations-and-pagination
https://docs.aws.amazon.com/appsync/latest/devguide/troubleshooting-and-common-mistakes.html
https://docs.amplify.aws/cli/graphql-transformer/dataaccess


# Parent Category
https://github.com/aws-amplify/amplify-cli/issues/1084

```graphql
BudgetCategory @model { id: ID! title: String! items: [BudgetItem]! @connection(name: "BudgetCategoryItems") children: [BudgetCategory]! parent: BudgetCategory @connection(name:"BudgetCategoryParent", keyField: "budgetCategoryParentId") }
```

# Exporting and Importing DynamoDB Data Using AWS Data Pipeline
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBPipeline.html


# Visualize DynamoDB data in AWS Quicksight
https://stackoverflow.com/questions/57775511/visualize-dynamodb-data-in-aws-quicksight
https://emshea.com/post/dynamodb-quicksight-pipeline
https://www.cdata.com/kb/tech/dynamodb-odbc-mysql-aws-quicksight.rst
https://panoply.io/integrations/amazon-dynamodb/amazon-quicksight/
https://blog.kloud.com.au/2018/04/09/amazon-quicksight-an-elegant-and-easy-to-use-business-analytics-tool/
https://dynamodb.toquicksight.com/


## New S3 data source: Config
Registers DynamoDB CSV export
https://s3.amazonaws.com/registers.dynamodb.backup/registersmanifest.json


# Show selected Image
- [*** works *** Medium](https://medium.com/@650egor/react-30-day-challenge-day-2-image-upload-preview-2d534f8eaaa)


# Refresh AWS S3 QuickSight
- [Refresh or Update QuickSight S3 data](https://docs.aws.amazon.com/quicksight/latest/user/refreshing-imported-data.html)


# Embed quicksight Dashboard
https://docs.aws.amazon.com/quicksight/latest/user/embedded-dashboards-setup.html
https://aws.amazon.com/blogs/big-data/embed-interactive-dashboards-in-your-application-with-amazon-quicksight/


# Aws AppSync Scalar Types
https://docs.aws.amazon.com/appsync/latest/devguide/scalars.html

# AppSync API (REST)

https://docs.amplify.aws/lib/restapi/fetch/q/platform/js#accessing-query-parameters--body-in-lambda-proxy-function


# Working with several DynamoDB Items

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.UpdateExpressions.html

https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SQLtoNoSQL.UpdateData.html


# How can I back up a DynamoDB table to Amazon S3?
How can I back up a DynamoDB table to Amazon S3?


# Migrating 

## aws amplify project to another account
https://aws.amazon.com/blogs/mobile/amplify-cli-adds-scaffolding-support-for-amplify-apps-and-authoring-plugins/
https://github.com/aws-amplify/amplify-cli/issues/3350
https://github.com/aws-amplify/amplify-cli/issues/2432


## DynamoDB migrations
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBPipeline.html


# Version V1.0 branch

su-ss-disinfection-register git:(development-v2) 

# Domain

- [Setting up custom domain Using aws-amplify console (EP-3)](https://www.youtube.com/watch?v=yPXzJ7uGUUE)


# Create new app
## jupiter-electronics.com
```sh
npx create-react-app jupiter-electronics.com
cd my-app
npm start
```
javigomez@yopmail.com