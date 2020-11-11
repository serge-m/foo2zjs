# foo2zjs 

This is a clone of the original printer driver `foo2zjs` from [http://foo2zjs.rkkda.com/](http://foo2zjs.rkkda.com/).

The up-to-date version was acquired on 11.11.2020 from the author's website.

For the original readme please refer to `README`.

## Installation

See [http://foo2zjs.rkkda.com/](http://foo2zjs.rkkda.com/)

## Installation for HP 1020 on Ubuntu 18

* Clone the repo

      git clone https://github.com/serge-m/foo2zjs.git foo2zjs
      cd foo2zjs
        

* Compile:

      make

* Get extra files from the web, such as .ICM profiles for color correction,
and firmware.  Select the model number for your printer:
 
      ./getweb 1020	# Get HP LaserJet 1020 firmware file


* Install driver, foomatic XML files, and extra files:
    
      sudo make install
    
    
* Configure hotplug (USB; HP LJ 1000/1005/1018/1020).
 
  **Note**: In the original documentation this step is marked as optional, 
  however it is required for Ubuntu 18 + HP 1020 to work properly. 
      
      sudo make install-hotplug
    
  Do `sudo apt remove system-config-printer-udev` if the command above fails.

* Restart CUPS

      sudo systemctl restart cups
  
  
* Add a new printer in the system settings or CUPS and print.
