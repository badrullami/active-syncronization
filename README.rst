========================
Active Syncronization
========================

The following are APIs for integration with existing applications or middleware from beacon devices (Cubeacon Reader AR25 and Cubeacon Card)

Services
----------

This is list of required method/function that will push from cubeacon server into client.

==================      ===============
Method                  Description
==================      ===============
onBeaconMonitoring	    this method is used for receive information from cubeacon server/devices when enter/exit beacon signal.
==================      ===============

List Resource
~~~~~~~~~~~~~~~

.. code-block:: text

    /v1/onBeaconMonitoring


POST 
++++++

This method will receive data from cubeacon server that will be triggered

==============   ===============
Param            Description
==============   ===============
floor            name or code of floor (string eg. floor01, floo02,...)
lift             name or code of lift (string eg. lift01, lift02,... )
state            state of enter/exit beacon signal (boolean)
==============   ===============

Sample cURL Request
~~~~~~~~~~~~~~~~~~

.. code-block:: text

  curl -X POST \
  {{endpoint}}/v1/onBeaconMonitoring \
  -H 'content-type: application/json' \
  -d '{
        "floor": "floor01",
        "lift": "lift02",
        "state": true
      }'

The endpoint will be access by cubeacon server that provide by client.

Sample Success Response
~~~~~~~~~~~~~~~~~~

.. code-block:: text

    {"message":"beacon data was received"}

Sample Error Response
~~~~~~~~~~~~~~~~~~

.. code-block:: text

    {"code":401, "error":"Unauthorized access"}
