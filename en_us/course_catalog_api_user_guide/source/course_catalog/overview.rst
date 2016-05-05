.. _Course Catalog API Overview:

#############################
Course Catalog API Overview
#############################

Use the Course Catalog API to obtain information about the catalogs that edX
offers, as well as information about the courses in a specific catalog.

Before you use the Course Catalog API, you must request credentials from edX.
For more information, see :ref:`Get Credentials for the EdX Course Catalog
API`.

Using the Course Catalog API, you can accomplish the following tasks.

.. list-table::
   :widths: 20 10 70
   :header-rows: 1

   * - Task
     - Method
     - Endpoint
   * - :ref:`Get a list of all available course catalogs <Get a List of All
     Course Catalogs>`
     - GET
     - /api/v1/catalogs/
   * - :ref:`Get information about a specific catalog <Get Information About a
     Specific Catalog>`
     - GET
     - /api/v1/catalogs/{id}/
   * - :ref:`Get a list of all courses in a catalog <Get a List of All Courses
     in a Catalog>`
     - GET
     - /api/v1/catalogs/{id}/courses/

For more information, see :ref:`Course Catalog API Catalogs Resource`.
