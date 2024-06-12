# Django-Voting-App

This voting application is a comprehensive platform for managing voting polls. Users must register to view and participate in polls. Once a user has voted, they cannot vote again. Only the poll creator has permissions to create, edit, update, delete polls and choices, and to conclude a poll. Once a poll is concluded, it can no longer be voted on, but users can view the final results. The app includes a search function for finding polls and allows users to filter polls by name, publish date, and vote count. Pagination is supported even when filters are applied.
<h1>Getting Started</h1>
<p>These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.</p>

<h2>Prerequisites</h2>
<code>python== 3.5 or up and django==2.0 or up</code>

<h2>Installing</h2>
<pre>open terminal and type</pre>
<code>git clone https://github.com/FOSSMentorOfficial/django-voting-app.git</code><br><br>

<h4>or simply download using the url below</h4>
<code>https://github.com/FOSSMentorOfficial/django-voting-app.git</code><br>

<h2>To migrate the database open terminal in project directory and type</h2>
<code>python manage.py makemigrations</code><br>
<code>python manage.py migrate</code>

<h2>To use admin panel you need to create superuser using this command </h2>
<code>python manage.py createsuperuser</code>

<h2>To Create some dummy text data for your app follow the step below:</h2>
<code>pip install faker</code>
<code>python manage.py shell</code>
<code>import seeder</code>
<code>seeder.seed_all(15)</code>
<p>Here 15 is a number of entry. You can use it as your own</p>

<h2> Configuring OAuth login </h2>
<details>
    <summary>Obtaining OAuth Client ID for Google</summary>

1. **Go to the Google Cloud Console:**
   - Navigate to [Google Cloud Console](https://console.cloud.google.com/).
   - Sign in with your Google account.

2. **Create a new project:**
   - Click on the project dropdown menu at the top of the page.
   - Click on "New Project" and follow the prompts to create a new project.

3. **Enable the Google Identity service:**
   - In the Google Cloud Console, navigate to "APIs & Services" > "Dashboard."
   - Click on "Enable APIs and Services."
   - Search for "Google Identity" or "Google+ API" and enable it for your project.

4. **Create OAuth consent screen:**
   - In the Google Cloud Console, navigate to "APIs & Services" > "OAuth consent screen."
   - Fill in the required fields (like application name, user support email, etc.).
   - Add scopes (permissions) your application requires.
   - Save the consent screen information.

5. **Create OAuth credentials:**
   - In the Google Cloud Console, navigate to "APIs & Services" > "Credentials."
   - Click on "Create Credentials" > "OAuth client ID."
   - Select "Web application" as the application type.
   - Enter a name for your OAuth client.
   - Add authorized redirect URIs : `http://127.0.0.1:8000/complete/google-oauth2/`
   - Click "Create."

6. **Copy the client ID and client secret:**
   - Once the OAuth client is created, you'll see your client ID and client secret.
   - Copy these values and update the following variables in settings.py

        ```
        SOCIAL_AUTH_GOOGLE_OAUTH2_KEY = 'your-client-id'
        SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET = 'your-client-secret'
        ```

For detailed instructions, refer to Google's documentation on [OAuth 2.0](https://developers.google.com/identity/protocols/oauth2).
</details>

<details>
   <summary>Obtaining OAuth Client ID for Facebook</summary>
   
1. **Create a Facebook App:**
   - Go to the [Facebook Developers](https://developers.facebook.com/) website and log in.
   - Click on "My Apps" and then "Create App".
   - Enter the required information for your app (display name, contact email, etc.) and create the app.

2. **Configure Basic Settings:**
   - In your app dashboard, go to Settings > Basic.
   - Add a platform (select Website) and enter your site URL(http://127.0.0.1:8000/complete/facebook/).
   - Save your changes.

3. **Get App ID and App Secret:**
    
    - Update the following settings to your settings file, replacing `'your-facebook-client-id'` and `'your-facebook-client-secret'` with your actual LinkedIn app credentials:
     ```python
        SOCIAL_AUTH_FACEBOOK_OAUTH2_KEY = 'your-client-id'
        SOCIAL_AUTH_FACEBOOK_OAUTH2_SECRET = 'your-client-secret'
     ```


</details>
<details>
  <summary>Obtaining OAuth Client ID for LinkedIn</summary>

  ### Step 1: Create a LinkedIn App
  1. Go to the [LinkedIn Developer Portal](https://www.linkedin.com/developers/) and sign in.
  2. Click on "Create App" and fill in the required details, such as the app name, description, and logo.
  3. In the "Authorized Redirect URLs" section, add the callback URL for your Django app. This URL will be like `http://127.0.0.1:8000/complete/linkedin/`.
  4. Save the changes and note down the Client ID and Client Secret provided by LinkedIn.

  ### Step 2: Configure Django Settings
  
    1. Update the following settings to your settings file, replacing `'your-linkedin-client-id'` and `'your-linkedin-client-secret'` with your actual LinkedIn app credentials:
     ```python
     SOCIAL_AUTH_LINKEDIN_OAUTH2_KEY = 'your-client-id'
     SOCIAL_AUTH_LINKEDIN_OAUTH2_SECRET = 'your-client-secret'
     ```
</details>

<h2> To run the program in local server use the following command </h2>
<code>python manage.py runserver</code>

<p>Then go to http://127.0.0.1:8000 in your browser</p>

<h2>Project Snapshots</h2>
<h3>Home page</h3>
<div align="center">

![Main Screen](/static/img/screenshots/home-page.png)

</div>

<h3>Login Page</h3>
<div align="center">

![Login Screen](/static/img/screenshots/login-page.png)

</div>

<h3>Registration Page</h3>
<div align="center">

![Login Screen](/static/img/screenshots/registration-page.png)
</div>

<h3>Voting List Page</h3>
<div align="center">

![Login Screen](/static/img/screenshots/voting-lists.png)
</div>

<h3>Voting Add Page</h3>
<div align="center">

![Login Screen](/static/img/screenshots/add-new-vote.png)
</div>

<h3>Voting Edit Page</h3>
<div align="center">

![Login Screen](/static/img/screenshots/edit-vote.png)
</div>
