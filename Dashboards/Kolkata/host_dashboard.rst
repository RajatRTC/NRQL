Demo of New Relic Agent Dashboard
======================

**Introduce About New Relic Agent**

A ``New relic`` agent is a piece of software that you install on a host or in an application that sends performance data to New Relic. `New Relic`_ is a Software as a Service offering that focuses on performance and availability monitoring.

.. _New Relic: http://newrelic.com

**Dashboard of Host**
-----

**Example 1:** ``CPU Usage(Latest)``

.. code:: bash

    SELECT latest(cpuSystemPercent) AS 'System', latest(cpuIOWaitPercent) AS 'I/O wait', latest(cpuUserPercent) AS 'User', latest(cpuStealPercent) AS 'Steal' FROM SystemSample WHERE entityKey = 'vibkol' TIMESERIES SINCE 7200 seconds ago EXTRAPOLATE

**Example 2:** ``Network Traffic/Utilization``

.. code:: bash

    SELECT latest(host.net.transmitBytesPerSecond) AS 'Transmit bytes per second', latest(host.net.receiveBytesPerSecond) AS 'Receive bytes per second' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' TIMESERIES auto

**Example 3:** ``Current Process Running``

.. code:: bash

    SELECT latest(host.process.cpuPercent) as 'CPU %', latest(host.process.threadCount) as 'Threads' FROM Metric FACET processId, processDisplayName WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' ORDER BY cpuPercent asc LIMIT 150

**Example 4:** ``Memory(in bytes)``

.. code:: bash

    SELECT latest(host.memoryUsedBytes) AS 'Memory Used', latest(host.memoryFreeBytes) AS 'Memory Free' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' TIMESERIES Since 8 hour ago
  
**Example 5:** ``Storage Used (in bytes)``

.. code:: bash

    SELECT latest(diskUsedBytes) as 'Disk Used' FROM SystemSample WHERE fullHostname = 'vibkol' SINCE 1800 seconds ago EXTRAPOLATE
  
**Example 6:** ``Storage Free (in bytes)``

.. code:: bash

    SELECT latest(diskFreeBytes) as 'Disk Free' FROM SystemSample WHERE fullHostname = 'vibkol' SINCE 1800 seconds ago EXTRAPOLATE
  
**Example 7:** ``Latest Load``

.. code:: bash

    SELECT latest(host.loadAverageOneMinute) as '1 minute', latest(host.loadAverageFiveMinute) AS '5 minutes', latest(host.loadAverageFifteenMinute) AS '15 minutes' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' TIMESERIES auto

**Example 8:** ``CPU Usage (Latest)``

.. code:: bash

    SELECT latest(host.cpuPercent) AS 'CPU used %' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' TIMESERIES AUTO SINCE 24 hour ago  WITH TIMEZONE 'Asia/Kolkata'
    
**Example 9:** ``Storage (in Bytes)``

.. code:: bash

    SELECT Latest(host.disk.usedBytes) as 'Storage used', latest(host.disk.freeBytes) As 'Storage Free' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXwyNjg0Nzg1NDkwMjg3NTczMTU3' TIMESERIES Since 24 hour ago    

**Example 10:** ``Disk Used (in Bytes)``

.. code:: bash

    SELECT latest(diskUsedBytes) as 'Disk Used', latest(diskFreeBytes) as 'Disk Free' FROM SystemSample WHERE fullHostname = 'vibkol' SINCE 1800 seconds ago EXTRAPOLATE
    
    
**Example 11:** ``Memory Usage (Max)``

.. code:: bash

    SELECT max(memoryUsedBytes / memoryTotalBytes * 100) AS 'Used %', max(memoryFreeBytes / memoryTotalBytes * 100) AS 'Free %' FROM SystemSample WHERE fullHostname = 'vibkol' TIMESERIES SINCE 7200 seconds ago EXTRAPOLATE
