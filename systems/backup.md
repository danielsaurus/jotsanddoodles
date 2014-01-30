Backup System
=============
template: reference

To feel confident in my system, I wanted to have the following backups:

* Time Machine
* Off site
* Cloud
* Bootable disk image

These things need to be as automated as possible so that it's not something I have to think about doing.

For context, my current hardware setup which I'm backing up is a Mac mini, Synology NAS, iPhone, and iPad. (The laptop I use is company-issued and any working files are saved on Dropbox or the file server.)

**My goal with this system**: at any time, I could either dispose of or have catastrophic failure to any (or many) of my devices or machines and not lose any critical or irreplaceable data. Some systems would take more time to recover (NAS for example, where iPhone could just download backup from iCloud).

Mac mini
========

* Has 256GB drive
* Contains mostly documents with small file sizes, working documents
* Does contain iPhoto Library (~30GB) but no other media

###  Backup Method ###

* [Backblaze](http://backblaze.com) for cloud backup of machine
* [Superduper](http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html) to make bootable drive on 500GB external in a custom, heavy duty enclosure (see below) which gets taken offsite and updated every week or two
  * I use a repeating to-do in OmniFocus to remind me to grab it from my office and take it back
  * Have Superduper setup to SmartUpdate when drive is attached, then eject, and quit when it's done so all I have to do is plug it in
* Time Machine backup to expandable, RAID volume on NAS
* Use [Lingon](https://itunes.apple.com/us/app/lingon-3/id450201424?mt=12) to trigger a basic script (see below) that gzips select directories and moves from Mac to Storage on NAS for additional layer of backup (folders which I want to exist on Mac for backup purposes on cloud and offsite)

Synology NAS
============

* [Synology RS812](http://www.synology.com/products/product.php?product_name=RS812)
* 4 x 3TB WD Red
* Uses Synology dynamic RAID for redundancy
* 4 virtual volumes
  * iTunes
  * Storage
  * System
  * Time Machine
* Files on System and iTunes are considered replaceable
* Use Glacier package to back up volumes of important, irreplaceable files to AWS

Devices (iPhone/iPad)
=====================

* Backup to iCloud
* Ocassionally backed up manually with iTunes 
  * `MobileSync` directory is symlinked to network drive for space saving on SSD and backup.


Heavy Duty Custom Enclosure
===========================

![Enclosure](http://f.cl.ly/items/3I0g0R1B310e0J2s2y1x/image.jpg)


***

Is all of this overkill? I don't know, maybe. But it didn't take that much time to set up and I've heard so many horror stories about lost data that I'd rather overdo it than screw it up.



