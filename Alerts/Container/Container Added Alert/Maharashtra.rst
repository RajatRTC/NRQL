Container Added Alert with New Relic Agent
======================

**Maharashtra Server**
---------
**Step 1:** Go to Dashboard.

**Step 2:** Select Dashboard.

**Step 3:** Create/ Select Releted Query.

**Step 4:** Click on ``dotted line icon`` of releted query.

**Step 5:** Click on ``Create Alert Condition``

**Step 6:** Enter Condition Name

.. code:: bash

    Maharashtra Server Alert
    
**Step 7:** Define Signal

``Enter NRQL Query``

.. code:: bash

    SELECT uniqueCount(containerId) FROM ContainerSample WHERE fullHostname = 'server.debian.com'
    
**Step 8:** Set your condition thresholds

Select thresholds as ``Static``

Open violation when the ``query return the values``

Critical: ``above`` ``36`` ``for atleast`` ``1 minutes``

**Step 9:** Connect your condition to a policy

If you have alreay created policy then select existing policy, otherwise create new policy.

**Step 10:** Save Condition

Now your Alert condition is created.


**To View Alert conditions**

**Step 1:** Go to Top Navbar.

**Step 2:** Click on ``Alert & AI``.

**Step 3:** Click on ``Alert Conditions(Policies)``.

**Step 4:** Find your ``created Policies``.

Thanks
-----

Go to `Bangalore Server`_

Go to `Kolkata Server`_

.. _Bangalore Server: http://newrelic.com
.. _Kolkata Server: http://newrelic.com
