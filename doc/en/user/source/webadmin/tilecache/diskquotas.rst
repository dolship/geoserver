.. _webadmin_tilecaching_diskquotas:

Disk Quotas
===========

The Disk Quotas page manages the disk usage for cached tiles and allows you to set the global disk quota. Individual layer quotas can be set in the layer's :ref:`properties <webadmin_layers>` page. 

By default, disk usage for cached tiles is unbounded, but this can cause disk capacity issues, especially when using Direct WMS integration (see :ref:`webadmin_tilecaching_diskquotas` for more on this). Setting a disk quota establishes disk usage limits.


When finished making any changes, remember to click :guilabel:`Submit`.

.. figure:: img/diskquota.png
   :align: center

   *Disk quota*

Enable disk quota
-----------------

When enabled, the disk quota will be set according to the options listed below. The setting is disabled by default.

Disk block size
---------------

This setting determines how the tile cache calculates disk usage. This field should be set equal to the disk block size of the storage medium where the cache is located. The default is **4096 bytes**. 

Disk quota check frequency
--------------------------

The time interval where the cache is polled for any overage. Smaller values (more frequent polling) will slightly increase disk activity, but larger values (less frequent polling) may cause the disk quota to be temporarily exceeded. The default is **10 seconds**.

Maximum tile cache size
-----------------------

The maximum size for the cache. When this value is exceeded and the cache is polled, tiles will be removed according to the policy. Note that the unit options are **mebibytes (MiB)** (approx. 1.05MB), **gibibytes (GiB)** (approx. 1.07GB), and **tebibytes (TiB)** (approx. 1.10TB). Default is **500 MiB**.

The graphic below this setting illustrates the current size of the cache relative to the disk quota.

Tile removal policy
-------------------

When the disk quota is exceeded, this policy determines how the tiles to be deleted are identified. Options are **Least Frequently Used** (removes tiles based on how often the tile was accessed) or **Least Recently Used** (removes tiles based on date of last access). The optimum configuration is dependent on your data and server usage.

