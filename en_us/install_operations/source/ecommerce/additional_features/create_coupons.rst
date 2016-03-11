.. _Create Coupons:

######################
Creating Coupon Codes
######################

.. This feature is not in Dogwood.

You can use coupons to provide discounted or free course enrollments to your
learners. Each coupon includes one or more coupon codes for learners to use.
Two types of coupon codes are available.

* Discount code: These codes offer a discount of up to 99% off the cost of a
  course.
* Enrollment code: These codes offer a 100% discount off the cost of a course.

Both discount codes and enrollment codes can be used in the following ways.

* One time by one user.
* One time by multiple users.
* Multiple times by multiple users.

When you create a coupon, the E-Commerce service generates an order. The
Invoice Payment Processor module records these orders and assumes out-of-band
payment for the coupons. The Invoice Payment Processor module also records
the transaction in the Invoice table for later reconciliation.

**************
Create Coupons
**************

You create coupons by using the coupon administration tool, which is located at
``http://localhost:8002/coupons/``.

#. In your browser, go to ``http://localhost:8002/coupons/`` to open the coupon
   administration tool, and then select **Create Coupon**.
#. On the **Create New Coupon** page, enter the following information.

   .. note::
     All of the following fields are required. After you create a coupon,
     you can only change the **Valid from** and **Valid until** dates.

   * **Name**: The name you want to give the coupon, such as "Holiday 2015 15%
     Promotion". The name must have fewer than 255 characters.
   * **Course ID**: The ID of the course that you want to provide the coupon
     for. To find the course ID, open the course administration tool at
     ``localhost:8002/courses``, select your course name in the list of
     courses, and then locate the **Course ID** field on the page for the
     course.
   * **Code Type**: Select either **Discount Code** or **Enrollment Code**. An
     enrollment code covers the entire price of a course seat. A discount code
     covers up to 99% of the price of a course seat.
   * **Seat Type**: The type of "seat" in the course. For example, this may be
     "verified" or "professional". The options for this field appear after you
     enter a valid value in the **Course ID** field.
   * **Category**: Suggested categories for your coupon code. These categories
     can help you keep track of your codes.
   * **Valid from** and **Valid until**: The dates and times when you want to
     start and stop offering the coupon, respectively. The time zone is
     set to Universal Coordinated Time (UTC). You can edit these fields after
     you create the coupon.
   * **Discount Value**: This field is only visible if you select **Discount
     Code** for **Code Type**. Enter the percent or U.S. dollar amount of the
     discount that you want to offer, then select **Percent** or **Fixed**.

#. (Optional) On the **Create New Coupon** page, enter the following
   information. All of these fields are optional.

   * **Note**: Any additional information that you want to add to your coupon,
     such as why the coupon was created. The note is visible on the coupon page
     in the coupon administration tool and in the .csv file for the coupon. It
     is not visible to the learner.
   * **Usage Limitations**: The way your coupon can be used. Options are
     **Can be used once by one customer**, **Can be used once by multiple
     customers**, or **Can be used multiple times by multiple customers**.
   * **Number of codes**: This field is visible if you select **Can be used
     once by one customer**. This value specifies the number of individual
     codes you want to create. Make sure that you create enough codes so that
     each person receives one code.
   * **Code**: This field is visible if you select **Can be used once by
     multiple customers** or **Can be used multiple times by multiple
     customers**.

     * If you select **Can be used once by multiple customers**, leave this
       field empty. The system generates the code for you when you select
       **Create Coupon**.

     * If you select **Can be used multiple times by multiple customers**, you
       can either enter a value in this field or leave it empty. You can enter
       alphanumeric characters as well as special characters such as
       underscores (_). For example, you can enter ``HOLIDAY_15``. If you leave
       this field empty, the system generates a code for you.

   * **Client**: The name of the organization that you create the codes for.
     This organization receives an invoice for the codes you create.
   * **Total Value of Coupon**: The value of all of the codes and course seats
     that are associated with this coupon, calculated as a product of the
     number of discount or enrollment codes, the number of course seats that
     each code applies to, and the discount amount per course seat. The system
     calculates this value automatically, and the value cannot be changed.
   * **Total to Invoice to Client**: The amount that the client pays for this
     coupon. If this value is the same as the value for **Total Value of
     Coupon**, you can leave this field blank. If you want to invoice the
     client for a different amount, enter that amount in this field.

#. Select **Create Coupon**.

When you select **Create Coupon**, a page for your coupon opens. This page
lists the information for your coupon, including any individual discount or
enrollment codes that the system generated as well as the URLs where users can
redeem each discount or enrollment code. To download a .csv file that lists
this information and additional information, select **Download**.


************
Edit Coupons
************

You edit coupons by using the coupon administration tool.

.. note::
 You can only edit the values in the **Valid from** and **Valid until** fields.

#. In your browser, go to ``http://localhost:8002/coupons/`` to open the coupon
   administration tool.
#. On the **Coupon Codes** page, locate the coupon that you want in the table,
   and then select the name of the coupon.
#. On the page for the coupon, select **Edit Coupon**.

   The username of the person who created or last edited the coupon is visible,
   along with the date and time of creation or the last edit.

#. In the **Valid from** or **Valid until** field, enter the date and time that
   you want.
#. Select **Save Changes**.

.. _Download Coupon Code Information:

***********************************
Download Coupon Information
***********************************

After you create a coupon, you can download a .csv file that lists information
such as the name of the coupon, the status of the coupon, and the user who
created the coupon. The .csv file also lists information for all of the
discount or enrollment codes that are associated with your coupon, including
the URL where a user can redeem each code.

#. In your browser, go to ``http://localhost:8002/coupons/`` to open the coupon
   administration tool.
#. On the **Coupon Codes** page, locate the coupon that you want in the table,
   and then select the name of the coupon.
#. On the page for the coupon, select **Download**. Your .csv file begins
   downloading automatically.


***************************************
Distribute Coupon Codes to Learners
***************************************

Learners redeem coupon codes, whether the coupon code is a discount code or an
enrollment code, in several ways.

* You provide a coupon code that they enter on the **Checkout** page for the
  verified or professional certificate track. You might also provide the URL
  for the course About page to make signing up for the course easier.

* You provide a URL for an **offer landing page**. At this URL, an
  automatically generated page presents information about the course, lets the
  learner know that the coupon code has been applied, and provides the
  opportunity for the learner to enroll. Learners can access this URL if they
  do not have an edX account or they are not signed in. However, learners must
  sign in or create an edX account to redeem the coupon and enroll in the
  course.

  A URL for an offer landing page has the following format.

  ``http://localhost:8002/coupons/offer/?code=################``

* You provide a URL for a **redeem endpoint**. At this URL, an automatically
  generated page lets the learner know that the coupon code has been applied
  and provides the opportunity for the learner to enroll in the course.
  Learners must be signed in to edX to access a redeem endpoint URL.

  A URL for a redeem endpoint has the following format.

  ``http://localhost:8002/coupons/redeem/?code=################``

.. note::
  If the coupon code is a discount code, the learner must pay any balance due
  before enrolling in the course for a verified or professional certificate.

To distribute the coupon code or URL to learners, you determine the coupon code
or the URL for the learner to use, and then you create and send an email that
includes the coupon code or the URL. For suggestions for email message text,
see :ref:`Example Email Messages`.

.. _Find a Coupon Code or URL:

===========================
Find a Coupon Code or URL
===========================

The coupon codes, whether discount codes or enrollment codes, and URLs for
individual coupons appear in two places: on the page for the coupon in the
coupon administration tool, and in a downloadable .csv file. You can use either
option to find the coupon code or URL for your learners.


Find a Code or URL on the Coupon Page
*************************************

To find a coupon code or URL on the page for the coupon in the coupon
administration tool, follow these steps.

#. In your browser, go to ``http://localhost:8002/coupons/`` to open the coupon
   administration tool.
#. On the **Coupon Codes** page, locate the coupon that you want in the table,
   and then select the name of the coupon.
#. On the page for the coupon, locate the table under **Codes**.
#. In the table, locate the information that you want.

   * For a coupon code that the learner will enter on the **Checkout** page,
     use the value in the **Code** column.

   * For an offer landing page, use the URL in the **Redemption URL** column.

   * For a redeem endpoint, copy the URL in the **Redemption URL** column, and
     replace ``offer`` in the URL with ``redeem``.


Find a Code or URL in a Downloaded File
***************************************

To find a coupon code or URL in the .csv file for a coupon, follow these steps.

#. :ref:`Download a .csv file <Download Coupon Code Information>` that lists
   the information for your coupon, and then open the .csv file.
#. In the .csv file, locate the information that you want.

   * For a coupon code that the learner will enter on the **Checkout** page,
     use the value in the **Code** column.

   * For an offer landing page, use the URL in the **URL** column.

   * For a redeem endpoint, copy the URL in the **URL** column, and replace
     ``offer`` in the URL with ``redeem``.


.. _Send an Email Message:

===========================
Send an Email Message
===========================

After you determine the coupon code or URL that you want to use, you provide
that information in an email message. When you send the message, keep the
following best practices in mind.

* If you send a coupon code for the learner to use on the **Checkout** page,
  edX recommends that you include the About page URL for the course as well as
  the coupon code to help learners enroll more easily.
* If you want to send a redeem endpoint, you must change the URL from the
  **Redemption URL** or **URL** column. In the URL, change the word ``offer``
  to ``redeem``. Do not make any other changes to the URL.

.. _Example Email Messages:

Example Email Messages
************************

You can use the following email messages as examples of the communication that
you send to your learners.

Learners Enter a Coupon Code on the Checkout Page
=================================================

.. code::

 Dear learner,

 You have received a discount <or an enrollment> code for edX101: Overview of
 Creating an edX Course. For more information about the course, see
 https://www.edx.org/course/overview-creating-edx-course-edx-edx101.

 To redeem this code, sign up for a verified <or professional> certificate, and
 then enter the following coupon code in the **Coupon Code** field on the
 **Checkout** page:

 ZDPC3AQV3732RQT5

 We look forward to learning with you!

 The edX101 course team


Learners Visit an Offer Landing Page
====================================

.. code::

 Dear learner,

 You have received a discount <or an enrollment> code for edX101: Overview of
 Creating an edX Course. To redeem this code and enroll in the course, visit
 the following URL:

 http://localhost:8002/coupons/offer/?code=ZDPC3AQV3732RQT5

 We look forward to learning with you!

 The edX101 course team

Learners Go to a Redeem Endpoint
================================

.. code::

 Dear learner,

 You have received a discount <or an enrollment> code for edX101: Overview of
 Creating an edX Course. To redeem this code and enroll in the course, visit
 the following URL:

 http://localhost:8002/coupons/redeem/?code=ZDPC3AQV3732RQT5

 We look forward to learning with you!

 The edX101 course team
