# Logging In

This document will describe the process for logging in with KeyCloak.

We have several key terms to note here:

* User: the user that is attempting to login.
* KeyCloak: the KeyCloak server that provides identity access management
* Nexus: the frontend server
* Shadow: the backend server
* Control: the current program that is being run (as in, which application is now running and executing commands)

## Steps

1. The User sends a request to Nexus to access the login page. Nexus receives Control and responds with the information for the login page to the browser. The User now receives control.
2. The User clicks on the button to login in the login page. The browser sends a request to KeyCloak, whom receives Control.
3. The User proceeds to login.
4. Once KeyCloak has finished processing, it redirects the user to the Redirect URL, which is a Shadow endpoint. KeyCloak will include information such as the auth_token.
   1. This may not be the case, according the [KeyCloak Documentation](https://www.keycloak.org/docs/latest/server_admin/#_saml), which states that the information will be sent back to the application that requested the information, which in this case, would be Nexus.
   2. Possible solutions to this would be to receive the information from KeyCloak and send the information back to Shadow. This should shift control and we would need to change the picture later on.
5. Shadow, upon receiving the information, will generate its own auth token for internal processing.
6. Shadow then sends this information to Nexus, also granting it Control.
7. Nexus sends a request back to Shadow querying the user_data for the auth_token that is received.
8. Shadow sends the information back to Nexus. The Nexus process completes and Control is released to Shadow.
9. Shadow then completes by sending the browser to Nexus Dashboard, which is populated with data. Control is sent to Nexus.
   1. Nexus may make further calls here as for information for the Dashboard elements.
10. Nexus displays this information to the User, who also gains Control.

THe Login Process is then complete.

## Issues

* Please refer to te caveat in Point 4, where it may not be the case the KeyCloak sends a POST Request with the Auth Token to the Redirect URL but instead responds to the Application that initiated the Login Process (which would be Nexus). The issue here is to determine where KeyCloak sends the information to!
  * This information be found within the *Fine Grain SAML Endpoint Configuration* section of your KeyCloak Client. Please check if this is true!
  * If this is true, then we will need to restructure the way that this process is set up. 


## Resources 

* [Secure your Flask application with Keycloak and SAML 2.0](https://xwf.medium.com/secure-flask-application-with-keycloak-and-saml-2-0-3c1986f47cd)
* [Tech Review Whiteboard](https://jamboard.google.com/d/1f84aebGrvZnxSoeiZDprQs5bjHZmjYCIojCXgP30QxA/viewer?f=3)
* [KeyCloak SSO Protocols - SAML](https://www.keycloak.org/docs/latest/server_admin/#_saml)
