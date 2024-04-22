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

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/8df54939-d5ad-48d5-b3b8-557f21f2fdc6)

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/549e3e35-fe7e-4c1c-8040-ff0694d617df)

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/69bd3b09-1306-436d-b4fe-59ee313923c0)

**[Configure OAuth and Service Accounts](https://developers.google.com/android-publisher/getting_started#service-account)**

Step 1: Create a certificate in the Google Cloud Console

- In the Google Cloud Console go to Service Accounts
- Click Create service account and follow the steps
- Select the service account and create key type JSON, save file key of service account.

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/9a79485f-5fb1-4f20-9103-6e5a24b44ca3)



Step 2: Go to the Users & Permissions page on the Google Play Console

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/2f04324b-0e39-4607-aafc-60cdf6013fcd)


Step 3: Click Invite new users

Step 4: Put an email address for your service account in the email address field and grant the necessary rights to perform actions

- Example: Get the email created from the service account as above step 1 get the account with email samuel-amelia-2024@samueapp.iam.gserviceaccount.com

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/2fea4712-538c-476b-a123-e9be9568f678)


- The image below is the result captured after completing inviting a user

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/25e7c413-bea0-470c-a64f-abfc3e948a9e)

Step 5: Click add app in tab App permissions and select role permissions you want

- Select app

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/70fd438a-1ede-45f1-9a9c-5759ce1cd914)

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/e582e4ab-734f-4652-887b-c45299457e6b)


- Select permissions

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/48a2d9ea-0fbe-49c4-8e23-83ac82c9ca5a)

![image](https://github.com/tuannd20/Tracking-gg/assets/74279060/90168192-6c7b-4586-b47e-c8d37fa08c02)


Step 6: Click Invite user.

## Link reference:

- **[Config API access](https://www.iwantanelephant.com/blog/2020/11/17/how-to-configure-api-access-to-google-play-console/)**
- **[Video select permissions](https://www.youtube.com/watch?v=Ls2wkAwXftk)**
- **[Creating a service account](https://developers.google.com/identity/protocols/oauth2/service-account)**
- **[Android in-app purchase implementation process steps](https://adapty.io/blog/android-in-app-subscriptions-tutorial/#android-in-app-purchase-implementation-process-steps)**
