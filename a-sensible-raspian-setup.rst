a sensible raspian configuration
################################

:date: 2017-02-06
:status: published
:tags: linux, raspberry pi, raspian
:category: programming
:slug: a-sensible-raspian-setup
:authors: Matt Baltrusitis
:summary: a straight-forward and sensible way to configure your headless raspberry pi running raspian.

Systems-on-a-chip, often referred to as SOCs to confuse outsiders, have gained in popularity the last few years. Probably the most well known of these tiny computers is the Raspberry Pi. The earlier generations appealed to educators which were "powerful enough" for teaching programming basics from the humble "Hello, world!" to a weather station to even charming little robotics projects. Today, as this category of device continues to mature, you can snag full 64-bit, quadcore systems for well under $50 USD; and options vary well beyond the Raspberry Pi. We are now seeing entrants into the market from big players like NVIDIA and ASUS to the smaller but also successful Pine64.

I personally picked up a few to use as cheaper alternatives to small cloud instances. Once having these setup as tiny little Linux boxes, they would make great little sandboxes for my projects while in the prototyping stage where performance isn't a focus. Who knows though, maybe after setting these guys up behind a dynamic DNS, I can throw some traffic their way and see how they hold up. Thats for another blog post though, lets get to work on getting these guys up and running.


Our initial setup
*****************

parts:
login - pi/raspberry
setup the wifi if needed:
    /etv/wpa-supplicant
    network={
        ssid="network name"
        psk= "your password"
        reboot
        ifconfig
sudo rasp-config
    change your default password
    enable the ssh server
    re-size the file system
secure your SSH
    etc/sshd (i think???)
    Port 33133
    AuthorizedKey <path>
    PermitEmptyPasswords no
    UsePAM no
    PermitRootLogin no
Add a new user
    Make them a sudoer
    sudo visudo
    <username> ALL=NOPASSWD:ALL
Download your public SSH keys from GitHub
    mkdir -p ~/.ssh
    curl -o
You should now be done!!!
Some other personal configurations...




