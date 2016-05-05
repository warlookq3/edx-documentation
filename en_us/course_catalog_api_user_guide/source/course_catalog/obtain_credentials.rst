.. _Get Credentials for the EdX Course Catalog API:

################################################
Get Credentials for the EdX Course Catalog API
################################################

Your API client credentials consist of a client ID and a client secret. EdX
generates your client credentials after you request access to the API.

To obtain your client credentials, complete the following steps.

.. contents::
   :local:
   :depth: 1

.. _Obtain EdX User Account and Sign In:

*****************************************
Obtain EdX User Account and Sign In
*****************************************

To obtain an edX user account, contact the edX marketing team. The team will
send you an account username and a temporary password.

To sign in to edX and change your password, go to
https://courses.edx.org/login.


.. _CC API Complete Access Request Form:

*****************************************
Complete the EdX API Access Request Form
*****************************************

After you have signed in to edX, follow these steps.

#. Go to http://courses.edx.org/api-admin.
#. On the **EdX API Access Request** page, enter the information for your
   organization. All fields are required.

    * **Company Name**: The name of your company. (---Any additional info, like
      legal name?)
    * **Website**: The URL for your company's website.
    * **Company Address**: Your company's mailing address. (---form just says
      "contact address" - are PO boxes OK?)
    * **Application Description**: A brief description of the main use for your
      application.

#. At the bottom of the form, select the **Terms of Service** check box.
#. Select **Save** to submit your request. (---Is the button name **Save** or
   **Submit** or something else?)

After you submit the request form, edX will review your request, and then edX
will send you an email message approving or denying your request. (---Time
frame for expected response?)

.. _CC API Generate API Credentials:

*****************************************
Generate API Credentials
*****************************************

When you receive your approval email message from edX, follow these steps.

#. Go to http://courses.edx.org/api-admin/status.
#. On the page that opens, enter the following information. All fields are
   required.

   * Name: The name of your application.
   * Redirect URLs: ---

#. Select **Generate API client credentials**.

After you receive your client credentials, you can use your client ID and
secret to set up your API.

