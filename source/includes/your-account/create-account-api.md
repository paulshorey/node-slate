The `secret_token` you will not send in any public requests, but only in administrative API requests to manage your account settings. We're also working on an admin app to let you manage your settings without programming.

- **Create an account**

  - You'll get back a `site_id` and a `secret_token`. The `site_id` is an optional parameter in our APIs.

  - You will pass the `site_id` when GETting data from our server. We'll use your custom data and preferences, instead of our own.

  - Your `secret_token` shall not be sent in any public requests, but only in administrative API requests. It's your password, to manage your account settings.

- **Set options**

  - Configure options and preferences, like the minimum/maximum length of suggested domain names, sort options, preferences, etc.

  - Configure which TLDs your site supports, and which you'd like to promote

- **View what options you have set**

  - View your account info, and all configured options
