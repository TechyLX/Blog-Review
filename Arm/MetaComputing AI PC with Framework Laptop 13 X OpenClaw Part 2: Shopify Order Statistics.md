# MetaComputing AI PC with Framework Laptop 13 X OpenClaw Part 2: Shopify Order Statistics


Last time, we built a smooth Discord smart chatbot with OpenClaw! This time, we'll integrate OpenClaw with Shopify to automate order data statistics, bidding farewell to the tedious process of manual calculation for good.

## Device Information
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/6fe8a7e8-7c13-4aad-8745-dfd4a97097ab" />
<img width="2256" height="1504" alt="image" src="https://github.com/user-attachments/assets/8afa5640-6baf-4c6a-ae1c-d1a0abef609d" />



## Create Custom Apps in Shopify Admin
- **Access the Apps Management Page**: Log in to your Shopify merchant admin, click "Settings" at the bottom of the left sidebar. Then select the "Apps" tab to enter the apps management page.
<img width="1280" height="684" alt="image" src="https://github.com/user-attachments/assets/2fd0086b-028e-4e1f-a8e9-2b4fbd4fc250" />


- **Enter Developer Mode**: Click the "Develop apps" button on the page to access the Shopify app developer interface. 
<img width="1280" height="847" alt="image" src="https://github.com/user-attachments/assets/6260b306-78d1-4a0e-96c2-773185030298" />

- **Switch to the New Development Dashboard**: Click "Build apps in Dev Dashboard" to create your app using Shopify's brand-new developer dashboard. ：
<img width="1280" height="447" alt="image" src="https://github.com/user-attachments/assets/af2bdda1-702e-419a-a55e-c5b1527a6af0" />

- **Create and Name the App**: Click "Create app" and fill in your app's name. 
<img width="1280" height="300" alt="image" src="https://github.com/user-attachments/assets/e89dd24b-3cf6-42d2-ab4e-3eddeca445ba" />
<img width="1280" height="608" alt="image" src="https://github.com/user-attachments/assets/e688a06e-a530-47c0-9618-9a2ed03a5874" />

- **Set App Permissions**: We recommend setting read-only permissions for the app as follows: 
<img width="1280" height="555" alt="image" src="https://github.com/user-attachments/assets/e249f908-8581-4ae5-b901-a33d361910d5" />
<img width="1280" height="294" alt="image" src="https://github.com/user-attachments/assets/d41b2a32-1082-4fce-9b82-b59edc9b013d" />


- **Save Settings**
<img width="1280" height="573" alt="image" src="https://github.com/user-attachments/assets/2687c93c-6af0-403a-84e6-5afdbe457450" />

- **Install the Custom App** 
<img width="1280" height="552" alt="image" src="https://github.com/user-attachments/assets/ab3bf726-cc34-4d11-956f-8abe70c923f4" />

<img width="1116" height="853" alt="image" src="https://github.com/user-attachments/assets/0e70f3d0-94a8-4ba4-8503-506ae307758b" />

<img width="1280" height="796" alt="image" src="https://github.com/user-attachments/assets/0497c2ec-52b5-4c68-be0f-9070e012fa61" />


- Obtain API Token: After installation, an Offline access token will be generated on the page. Please copy and store it securely, as you'll need it for binding with OpenClaw later. If the token doesn't appear automatically, you can manually generate it in the "API Credentials" section of the app, or refer to Shopify's official documentation: https://shopify.dev/docs/apps/build/authentication-authorization/access-tokens/offline-access-tokens

## Bind the App with OpenClaw
After creating the Shopify App, you can bind it with OpenClaw by following these steps:

- Enter the obtained API token into the OpenClaw chat box and send the binding command.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/82c5c342-08c1-47e2-8a49-1926f47e0ede" />


- After binding, send a test command to verify whether OpenClaw has successfully obtained access to your store data. Once the binding is successful, OpenClaw will have permission to read order and product data from your Shopify admin, allowing you to implement diverse data statistics functions as needed.

## Practical Function Demos
### Demo 1: Scheduled New Order Statistics with Automatic Push to Communication Platforms

- We can set up scheduling rules to let OpenClaw automatically count new orders and send the statistics to popular communication platforms like WhatsApp and Telegram, helping you keep track of store operations in real time.
<img width="636" height="596" alt="image" src="https://github.com/user-attachments/assets/89693694-f11d-4eed-9966-270114da9f5e" />


### Demo 2: Generate Visual Data Charts
- In addition to text-based statistics, OpenClaw can convert order data into visual charts, making data trends more intuitive to understand. 
<img width="1280" height="555" alt="image" src="https://github.com/user-attachments/assets/7a6d20e3-0cff-40f4-bd10-3b2bef1e86ce" />


### Conclusion
By integrating OpenClaw with Shopify, we can easily achieve automated order data statistics and visual display, greatly improving store operational efficiency!
