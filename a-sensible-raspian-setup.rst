a sensible raspian configuration.
#################################

:date: 2017-02-06
:status: published
:tags: raspberry pi, raspian
:category: programming
:slug: a-sensible-raspian-setup
:authors: Matt Baltrusitis
:summary: A straight-forward and sensible way to configure your headless Raspberry Pi running Raspian.

Systems-on-a-chip, often referred to as SOCs to confuse outsiders, have gained in popularity the last few years. Probably the most well known of these tiny computers is the Raspberry Pi. The earlier generations appealed to educators which were "powerful enough" for teaching programming basics from the humble "Hello, world!" to a weather station to even charming little robotics projects. Today, as this category of device continues to mature, you can snag full 64-bit, quadcore systems for well under $50 USD; and options vary well beyond the Raspberry Pi. We are now seeing entrants into the market from big players like NVIDIA and ASUS to the smaller but also successful Pine64.

I personally picked up a few to use as cheaper alternatives to small cloud instances. Once having these setup as tiny little Linux boxes, they would make great little sandboxes for my projects while in the prototyping stage where performance isn't a focus. Who knows though, maybe after setting these guys up behind a dynamic DNS, I can throw some traffic their way and see how they hold up. That is for another blog post though, lets get to work on getting these guys up and running.


our initial setup.
******************

There are a few things that should be handy while following this guide to make your life easier:

* A Raspberry Pi of course! I am using the Model B (the latest iteration as of this writing)
* MicroSD card imaged with the latest release of Raspian. There are great instructions to do this at raspberrypi.org
* Wireless network details:
  * SSID (network name)
  * network password and its type (i.e. WEP, WPA2, etc.)


preparing your sd card.
***********************

Recent versions of Raspian allow you to drop an empty file into the root of the `boot` image named `ssh` which will enable a very unsecured SSH daemon which we will remedy and lock down later. With the SD card plugged into another computer (I am assuming a UNIX-like system) this can be done with `touch`:

.. code-block:: bash

    $ touch /Volumes/boot/ssh

Eject the card and pop that sucker into the MicroSD slot of the Raspberry Pi you are configuring.


initial start-up.
*****************
