## Agriaku backoffice

## Apps

### backoffice_app/BackofficeAppModule

Inject ktor application class to the backoffice application and instantiate it

### backoffice_app/BackofficeApplication

Inject necessary modules to the backoffice app

## Adapters

### api/BackofficeAppAPIModule

Inject some API route class instances to the backoffice, i.e. InternalUserRegistrationAPIRoute, UserCheckSessionAPIRoute, UserLoginByPasswordAPIRoute, UserLogoutAPIRoute, InternalCategoryAPIRoute

### api/authentication/internal/InternalAuthenticationAPIModule

Inject InternalUserRegistrationAPIRoute instance into it. THIS MODULE IS CURRENTLY UNUSED 06/12/2021

### api/authentication/internal/InternalAuthenticationAPITag

Added a binding tag for the instance

### api/authentication/internal/InternalUserRegistrationAPIRoute

Create a new user with email and fullName

### api/authentication/v1/UserCheckSessionAPIRoute

Check if a user session is valid. THIS IS CURRENTLY A DUMMY 06/12/2021

### api/authentication/v1/UserLoginByPasswordAPIRoute

Login route for user

### api/authentication/v1/UserLogoutAPIRoute

Logout route for user. THIS IS CURRENTLY A DUMMY 06/12/2021

### api/category/InternalCategoryAPIRoute

create and read category/ categories
