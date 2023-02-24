# anycast_rabbithole

Inside the anycast rabbit hole - this repo is a follow up to [this blog](https://deploy.equinix.com/blog/down-the-anycast-rabbit-hole/) where I talked about debugging / using an anycast setup.


## PowerDNS

```
.. _setting-server-id:

``server-id``
-------------
-  String
-  Default: The hostname of the server

The reply given by The PowerDNS recursor to a query for 'id.server' with its hostname, useful for in clusters.
When a query contains the :rfc:`NSID EDNS0 Option <5001>`, this value is returned in the response as the NSID value.

This setting can be used to override the answer given to these queries.
Set to "disabled" to disable NSID and 'id.server' answers.

Query example (where 192.0.2.14 is your server):

.. code-block:: sh

    dig @192.0.2.14 CHAOS TXT id.server.
    dig @192.0.2.14 example.com IN A +nsid
```

