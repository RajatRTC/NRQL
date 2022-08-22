Container Excited Alert with New Relic Agent
======================

**Kolkata Server**
---------
**Step 1:** Go to Dashboard.

**Step 2:** Select Dashboard.

**Step 3:** Create/ Select Releted Query.

**Step 4:** Click on ``dotted line icon`` of releted query.

**Step 5:** Click on ``Create Alert Condition``

**Step 6:** Enter Condition Name

.. code:: bash

    Kolkata Server Alert
    
**Step 7:** Define Signal

``Enter NRQL Query``

.. code:: bash

    SELECT latest(host.cpuPercent) AS 'CPU used %' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3'  WITH TIMEZONE 'Asia/Kolkata'
    
**Step 8:** Set your condition thresholds

Select thresholds as ``Static``

Open violation when the ``query return the values``

Critical: ``equal`` ``0`` ``for atleast`` ``2 minutes``

**Step 9:** Connect your condition to a policy

If you have alreay created policy then select existing policy, otherwise create new policy.

**Step 10:** Save Condition

Now your Alert condition is created.


**To View Alert conditions**
-------

**Step 1:** Go to Top Navbar.

**Step 2:** Click on ``Alert & AI``.

**Step 3:** Click on ``Alert Conditions(Policies)``.

**Step 4:** Find your ``created Policies``.

Thanks
-----

Go to `Bangalore Server`_

Go to `Maharashtra Server`_

.. _Bangalore Server: https://github.com/RajatRTC/NRQL/blob/main/Alerts/System/Shutdown%20Alert/Bangalore.rst
.. _Maharashtra Server: https://github.com/RajatRTC/NRQL/blob/main/Alerts/Shutdown%20Alert/Maharashtra.rst
