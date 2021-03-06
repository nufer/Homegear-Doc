Removing KNX Devices
====================

.. highlight:: bash

KNX devices can either be removed using the Command Line Interface (CLI) or the RPC method ``deleteDevice()``. They are never removed automatically by Homegear. So if a device doesn't exist in your ETS project file anymore you need to delete it manually in Homegear.


Remove Device Using CLI
***********************

To remove a device with Homegear's CLI, start it by calling ``homegear -r``. Then execute::

	families select 14
	peers remove PEERID

The peer ID can be retrieved by calling ``ls`` before executing ``peers remove``.


Remove Device Using RPC
***********************

The simplest way to call ``deleteDevice()`` is by placing it into an inline PHP script. The argument ``flags`` is completely ignored and can be set to ``0``. To for example delete the device with peer ID 16 run on the command line::

	homegear -e rc '$hg->deleteDevice(16, 0);'