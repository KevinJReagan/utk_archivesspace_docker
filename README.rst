============================
UTK ArchivesSpace Docker Dev
============================

-----
About
-----

A development environment for UTK's ArchivesSpace instance:

- Installs our local plugin
- Adds a few of our EADs for testing
- Adds a few random accession records from production
- Configures application based on a config file similar to the one in production


**Note**: This is intended for testing purposes only. This is mostly for being able to demo and test things before
rolling to production.


----------
How to use
----------

To build and deploy **inititially**:

.. code-block:: console

    $ docker-compose up --build -d


To start, but **don't rebuild!!!**

.. code-block:: console

    $ docker-compose up -d


To turn off ArchivesSpace:

.. code-block:: console

    $ docker stop archivesspace


To delete all your computers you've ever built:

.. code-block:: console

    $ docker system prune -a


Add EADS for import at **/snake/data/eads**.

Add accession records as a dict in the accessions list in **/snake/data/accessions/accessions.py**.  Keep in mind that
you need to make sure no uris to digital objects in another ArchivesSpace instance are in the dict or ArchivesSpace will
freak out.

----------
Interfaces
----------

`Public Interface <http://0.0.0.0:8081/>`_

`Staff Interface <http://0.0.0.0:8080/>`_

`OAI-PMH Interface <http://localhost:8082/sample>`_

`Solr <http://0.0.0.0:8090/>`_

`REST API <http://0.0.0.0:8089/>`_

-------------
Default Login
-------------

username: admin
password: admin
