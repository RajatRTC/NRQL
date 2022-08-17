Demo of New Relic Agent Dashboard
======================

**Introduce About New Relic Agent**

A ``New relic`` agent is a piece of software that you install on a host or in an application that sends performance data to New Relic. `New Relic`_ is a Software as a Service offering that focuses on performance and availability monitoring.

.. _New Relic: http://newrelic.com

**Dashboard of Docker**
-----

**Example 1:** ``Docker Container CPU Usage(Latest)``

.. code:: bash

    FROM ContainerSample SELECT latest(cpuPercent) FACET name where host ='vibblr2' limit max

**Example 2:** ``Memory Usage(Latest)``

.. code:: bash

    FROM ContainerSample SELECT latest(memoryUsageBytes) FACET name WHERE hostname = 'vibblr2' limit max

**Example 3:** ``Total Containers``

.. code:: bash

    SELECT uniqueCount(containerId) FROM ContainerSample WHERE fullHostname = 'vibblr2' SINCE 1800 seconds ago EXTRAPOLATE

**Example 4:** ``Container Status``

.. code:: bash

    FROM ContainerSample SELECT name, state, status, cpuShares, restartCount, imageName where fullHostname ='vibblr2' and state != 'running' since 8 hours ago

**Example 5:** ``Network Rx/Tx(in bytes)``

.. code:: bash

    FROM ContainerSample SELECT latest(networkRxBytes), latest(networkTxBytes) WHERE host ='vibblr2' TIMESERIES AUTO
  
**Example 6:** ``Network Rx/Tx Error(in bytex)``

.. code:: bash

    FROM ContainerSample SELECT latest(networkRxErrors), latest(networkTxErrors) where host ='vibblr2' TIMESERIES AUTO SINCE today

**Example 7:** ``Available Containers``

.. code:: bash

    SELECT uniqueCount(containerId) FROM ContainerSample WHERE fullHostname = 'vibblr2' TIMESERIES AUTO SINCE today
