Base api này bao gồm:

- Source code phần handler, các API cần sửa lại handler này theo yêu cầu app tương ứng
- Source code phần crawler, bao gồm việc crawl 1 trang web, tải ảnh của web về, upload ảnh lên OVH cloud và tạo document trong mongodb.

Tạo file .env cho app như mẫu dưới đây

```
PORT=8888
JWT_SECRET=shhhhhh
DB_URI=mongodb://user:pwd@1.2.3.4:27017/testdatabase?retryWrites=true&w=majority
AES_ALGORITHM=aes-256-cbc
AES_SECRET=
AES_IV=
```

- DB_URI sửa lại theo config mongodb đã tạo ở trên.
- Thêm SECRET key và IV để sửa dụng mã hóa AES

## Setup access API Google Play

To access API access in the Google Play Console, you need to have the following:

**Create a Google Cloud Project**

- Create a project in the [Google Cloud Console.](https://console.cloud.google.com/projectcreate)

**Enable the API:**
To enable Google Play Developer API:

- Go to the [Google Play Developer API page](https://console.developers.google.com/apis/api/androidpublisher.googleapis.com/) in Google Cloud Console.
- Click Enable.

- **Flow: Go to page APIs & Services -> click Enable API and Service -> search "Google Play Android Developer API"**

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/24207ed9-d9cd-4849-911b-bc42aa1f6e05)

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/f0aae050-19fc-4f08-bf6d-75104887eac7)

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/ef97b48a-53b5-4c10-83d6-ae97f803051d)


**[Configure OAuth and Service Accounts](https://developers.google.com/android-publisher/getting_started#service-account)**

Step 1: Create a certificate in the Google Cloud Console

- In the Google Cloud Console go to Service Accounts
- Click Create service account and follow the steps
- Select the service account and create key type JSON, save file key of service account.

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/e718d02a-f70e-4fb4-8ae2-71557c3e4303)


Step 2: Go to the Users & Permissions page on the Google Play Console

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/19f2f41c-ab56-4873-8820-51f084c2a4ed)


Step 3: Click Invite new users

Step 4: Put an email address for your service account in the email address field and grant the necessary rights to perform actions

- Example: Get the email created from the service account as above step 1 get the account with email samuel-amelia-2024@samueapp.iam.gserviceaccount.com

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/2ea4c200-f311-4dc4-ba1a-bb5e644f77d5)


- The image below is the result captured after completing inviting a user

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/f40cd9f4-bf00-4b1f-b30e-b692c8aa5988)


Step 5: Click add app in tab App permissions and select role permissions you want

- Select app

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/e2a64334-1c8a-485c-bf72-96e82910459a)

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/3a34081f-8dad-40b6-8603-66e7def8397d)


- Select permissions

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/685e4814-349e-4d21-b980-050d7c69e030)

![image](https://github.com/Foxcode-Studio-Server/googletracking-backend/assets/139300981/bd0e9abe-3071-4bb3-b83e-e88e08d33f11)




Step 6: Click Invite user.

## Link reference:

- **[Config API access](https://www.iwantanelephant.com/blog/2020/11/17/how-to-configure-api-access-to-google-play-console/)**
- **[Video select permissions](https://www.youtube.com/watch?v=Ls2wkAwXftk)**
- **[Creating a service account](https://developers.google.com/identity/protocols/oauth2/service-account)**
- **[Android in-app purchase implementation process steps](https://adapty.io/blog/android-in-app-subscriptions-tutorial/#android-in-app-purchase-implementation-process-steps)**
