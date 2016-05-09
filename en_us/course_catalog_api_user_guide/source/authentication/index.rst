.. _edX API Authentication:

#############################################
Authenticating as an edX Web Service User
#############################################

EdX REST web services clients authenticate to access personalized information and secure resources. When a REST client authenticates with an edX REST web service, it does the following.

* The client presents a client identifier and a secret string to the
  ``/oauth2/v1/access_token`` resource and receives an access token.

* The client includes the access token when it makes another REST web services
  request.

The following diagram shows a REST client presenting its client ID and client secret to the ``/oauth2/v1/access_token`` resource. The ``access_token`` resource returns an access token.

.. image:: ../../../shared/images/api-authentication-get-token.png
  :width: 800
  :alt: A diagram showing a REST client application presenting ID and secret
      credentials to the authentication web service and receiving an access
      token.

The following diagram shows a REST client presenting an access token when it requests a REST resource. After it accepts the access token, the REST web service returns the resource data.

.. image:: ../../../shared/images/api-authentication-present-token.png
  :width: 800
  :alt: A diagram showing a REST client application presenting an access
      token when it requests a REST resource from api.edx.org.

The edX REST web services use the OAuth 2.0 standard for authentication. OAuth
2.0 is an open standard used by many systems that require secure user
authentication. See the `OAuth 2.0 Standard`_ for more information.

The example REST requests shown in this guide use the ``curl`` command-line program to send HTTP messages to edX web services. You can use any technology to send REST requests. The examples use the ``curl`` program to show the syntax and data for a request in a way that is easy to read. For more information about the ``curl`` program, see .

.. I think this might be a good place to explain how to get client credentials.

.. _getting_an_access_token:

*********************************************
Getting an Access Token
*********************************************

To get an access token, you send a POST request to the ``/oauth2/v1/access_token`` resource. The response you receive contains the access token string.

To get an access token for edX REST web services, follow these steps.

#. Make sure you have the client ID and client secret strings for your REST
   HTTP client.

#. Send a POST HTTP request

.. code-block:: json

    {
        "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmYW1pbHlfbmFtZSI6IkJsYWNrYnVybiIsImF1ZCI6Iklua29jdWpMaWt5dWNzRWR3aVdhdGRlYnJFYWNrbWV2TGFrRHVpZktvb3Noa2FrV293IiwiaXNzIjoiaHR0cHM6Ly9jb3Vyc2VzLnN0YWdlLmVkeC5vcmcvb2F1dGgyIiwicHJlZmVycmVkX3VzZXJuYW1lIjoiY2xpbnRvbmIiLCJnaXZlbl9uYW1lIjoiQ2xpbnRvbiIsImV4cCI6MTQ5NDA5ODQwOCwiaWF0IjoxNDYyNTYyNDA5LCJlbWFpbCI6ImNibGFja2J1cm5AZWR4Lm9yZyIsIm5hbWUiOiJDbGludG9uIEJsYWNrYnVybiJ9.mumH2jIpUtweprFAv1JwlFnm13a4-UyFktzegFa9doE",
        "expires_in": 31535999,
        "scope": "profile openid email permissions",
        "token_type": "JWT"
    }




.. _using_an_access_token:

*********************************************
Using an Access Token to Make REST Requests
*********************************************







***************************************
Registering with Your Open edX Instance
***************************************

To use the edX Platform API with courses on your instance of Open edX, you must
register your application with the Open edX server. See the OAuth 2.0
specification for details.

.. include:: ../../../links/links.rst
