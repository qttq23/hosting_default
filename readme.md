this talks about website hosting using Firebase Hosting.

# 1. Firebase Hosting
have free plan.
host static website.
add custom domain.
free SSL cert for default domain and custom domain.

https://firebase.google.com/docs/hosting

# 2. Practise
## used with Reactjs
- build Reactjs app to production code. eg: 'build' folder.

- install firebase cli (then login, list projects):
npm install -g firebase-tools
firebase login
firebase projects:list

https://firebase.google.com/docs/cli#install_the_firebase_cli

- go to your app root and init firebase hosting.
firebase init hosting
(when prompted, don't select one-page app or rewrite)
https://firebase.google.com/docs/hosting/quickstart#initialize

- deploy your 'build' folder.
firebase deploy --only hosting

now you have a public url to access your web app online.
if you want to assign a subdomain, use the instruction below:

- first, you must own a domain (eg: you buy a domain 'example.net' from Google Domain)

- go to firebase hosting console and add custom domain. it will take 1 or some hours to provide SSL cert for new custom domain.
https://firebase.google.com/docs/hosting/custom-domain

# 3. troubleshootings
when your publish your web to new domain, you may suffer some rejections from services such as your api server or Google Signin due to CORS.

CORS for api server: if you're using nodejs with expressjs, just install cors and it will solve the problem.

CORS for Google Cloud Storage: you have to use gsutil to set CORS for Storage. 
(view more: `storage_default`)

Google Signin/ Identity Platform: add the new domain to list of authorized origins/domains in Oauth Client credential and Identity Platform's Provider page.
(view more: `signin_oauth2_default`)




