
# Django Auth0 Integration
## Introduction
<img src="https://github.com/carlagesa/Django-Auth0-/blob/main/apiexample/auth0.229x256.png?raw=true" alt="Success!" width="500"/>

Auth0 is a powerful identity management platform that allows developers to add authentication and authorization services to their applications. This Django project showcases how to implement Auth0 authentication in a Django application, providing users with secure and seamless access.

This project demonstrates how to integrate Auth0 authentication into a Django application.


## API Reference
#### The routes shown below are available for the following requests:
#### Available for non-authenticated requests

```http
  GET /api/public
```

#### Available for authenticated requests containing an access token with no additional scopes

```http
  GET /api/private
```
#### Available for authenticated requests containing an access token with the read:messages scope granted
```http
  GET /api/private-scoped
```



# Running the example

In order to run the example, you need to have `python` and `pip` installed.

You also need to set your Auth0 Domain and the API's audience as environment variables with the following names
respectively: `AUTH0_DOMAIN` and `API_IDENTIFIER`, which is the audience of your API. You can find an example in the
`env.example` file.

For that, if you just create a file named `.env` in the directory and set the values like the following,
the app will just work:

```bash
# .env file
AUTH0_DOMAIN=example.auth0.com
API_IDENTIFIER=YOUR_API_AUDIENCE

```

Once you've set those 2 environment variables:

1. Install the needed dependencies with `pip install -r requirements.txt`
2. Migrate the database with `python manage.py migrate`
3. Start the server with `python manage.py runserver 3010`
4. Try calling [http://localhost:3010/api/public](http://localhost:3010/api/public)

# Testing the API

You can then try to do a GET to [http://localhost:3010/api/private](http://localhost:3010/api/private) which will
throw an error if you don't send an access token signed with RS256 with the appropriate issuer and audience in the
Authorization header. 

You can also try to do a GET to 
[http://localhost:3010/api/private-scoped/](http://localhost:3010/api/private-scoped) which will throw an error if
you don't send an access token with the scope `read:messages` signed with RS256 with the appropriate issuer and audience
in the Authorization header.

    
## Screenshots
 <h3> This is what will show upon successfull connection</h3> <br>
<img src="https://github.com/carlagesa/Django-Auth0-/blob/main/apiexample/Result.png?raw=true" alt="Success!" width="900"/>

<h3>This is what will show upon a failed connection</h3>
<img src="https://github.com/carlagesa/Django-Auth0-/blob/main/apiexample/Fail-Result.png?raw=true" alt="Failed connection!" width="900"/>

## Links
For more info check https://auth0.com/docs/quickstart/backend/django


## Authors

- [@carlagesa](https://www.github.com/carlagesa)

