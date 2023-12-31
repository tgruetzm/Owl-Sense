
<img src="logo.png" alt="Owl Sense" width="150" />

## Overview
  * Owl Sense offers an affordable and user-friendly audio recording solution for general purpose wildlife research.
  * Specifically built with extended runtimes and exceptional audio quality.
  * Recording times can exceed 500 hours at moderate sample rates(24k) or lower on a single 18650 cell.
  * Supports custom scheduling options to record only when necessary.
  * Fully weather resistant enclosure and microphone.

## Quick Start Guide
  1. Install a protected 18650 battery and memory card.
  2. The yellow Error LED will flash indicating the clock is not set.
  3. Hold the Wireless button until the blue LED illuminates, to turn on the radio.
  4. Load the Owl Sense app on your phone.
  5. Connect to and configure the device, set a Continuous schedule and toggle the recorder On.
  6. Press Update and disconnect from the recorder.
  7. The red Record LED should flash indicating a recording is in progress.


## Important Tips and Tricks
  1. The thumb screws are retained with a small o-ring. Pulling on the screws especially while turning can cause the o-ring to come off and get lost.
  2. Always check recorder at the time of deployment to ensure that it's recording or on standby and that the error led is off.  Sudden shocks, such as dropping can cause the battery to disconnect and the clock may reset.
  3. LED flashing uses negligible amounts of power, there is no issue with the error LED draining the battery before a deployment if the clock is not set or a card not inserted.
  4. Units come with a small desiccant pack.  It is recommended to remain in the unit.  Humidity can condense on the board after the case is closed.  Moisture on the board can cause it to misbehave and will likely shorten it's life.


## Hardware Overview
  - **Buttons**
    * On/Off - turns the recorder on or off.  Hold the button until the record LED lights up, then release.
    * Wireless - turns on the wireless radio.  Hold until the blue wireless LED lights up, then release.  Wireless can only be turned on to configure devices when off or on standby.  Configuration can not be done during an active recording.
    * Reset - a single press will reset the board.  Do not reset when a recording is in progress.  This may corrupt the memory card.  The green standy LED will illuminate after the system loads.
  - **LED indicators**
    * No LED -  if no LED is illuminated the recorder is off.  No recordings will take place.
    * Record - red LED, indicates that a recording is in progress.  The LED blinks everytime a file write occurs.  At a 48k sample rate it's one write/blink per second, at 12k it's one write/blink per 4 seconds, etc...
    * Standy - green LED, indicates that the recorder is on and is waiting for an active schedule.
    * Wireless - blue LED, solid indicates the wireless radio is powered.  Blinking indicates an active connection.
    * Error - yellow LED, blinking indicates an error.  Recordings will not happen if there is an error condition.  To see the exact error, use the Owl Sense app.
  - **Battery**
    * Only use protected 18650 cells from reputable manufacturers.  Cell length must be ~70mm.
    * Nevery use a battery if it shows any signs of damage or leakage.
    * End user is responsible for any damage or injury caused by misuse or mishandling lithium ion batteries and chargers.
    * Lithium batteries should always be stored individually and in a case or box that separates cells.
    * Lithium batteries may explode, burn, or cause a fire if misused or mishandled.
  - **Memory Card**
    * At this time only Samsung EVO Plus 64GB or 128GB cards are supported.  Others will work, but there is no guarantee of compatability.  Other cards may significantly reduce runtimes.
  - **Microphone**
    * Featuring Infineon's [IM73D122](https://www.infineon.com/cms/en/product/sensor/mems-microphones/mems-microphones-for-consumer/im73d122/) microphone
    * Ultra-low self-noise/ultra-high SNR 73dB(A)
    * Microphones are user serviceable, in the event of failure or better microphones becoming available.
    * The Microphone element is protected externally by an waterproof acoustic PTFE membrane.  This keeps water outside of the microphone port and decreases downtime in wet conditions.


## iOS App Overview
  - **Main Page**
    * Recorder List - shows an item for each recorder in range that has the wireless radio on.
    * Defaults - allows configuration of default values, these can be easily loaded to any recorder or are automatically loaded if no configuration file is found.
  - **Recorder Detail Page**
    * **Recorder Detail** - shows basic info about the recorder.
      - ID - this value is unique to each recorder(ID can be copied by long pressing).
      - Status - shows details for any error or OK.
      - Battery levels - shows voltage and approximate battery capacity remaining.  Capacity numbers are estimates using a Molicel M35A cell. Other cells may show significantly higher or lower capacity estimates.  
      - Current date/time - date/time set on the recorder.
      - dB level - shows approximate dB level of the microphone.  This is useful to gauge whether there is an issue with the microphone system(blockage or failure).  You should see this respond to changes in sound intensity.
      - Card details - shows basic storage information.
      - Firmware version
    * **Recorder Configuration**
      - On/off - identical function to the physical On/Off button.
      - File Prefix - all audio files will be prefixed with this name.  Supports 18 characters, alphanumeric and dash(File Prefix can be copied by long pressing).
      - Auto DST - Automatically adjusts the recorders clock when DST starts and ends.  Follows US DST standards.
      - Schedule
        1. Continuous
        2. Sunrise to Sunset
        3. Sunset to Sunrise
        4. Sunrise and Sunset
        5. Sunset
        6. Sunrise  
        *Sunrise/Sunset based schedules support a configurable start before/end after setting.  For example, you can configure a "Sunrise to Sunset" schedule to start 30 minutes before sunrise and end 60 minutes after sunset.
        7. Duty Cycle  
        *Supports a configurable On Period and Off Period in minutes.
      - Start Date - configurable date/time to delay before starting the schedule.  Green Standby LED will blink until the date/time passes.
      - File Splitting - 1, 2, 4, 6, 12 or 24 hour file splitting.  Files will automatically split at 4GB if exceeded.
    * **Microphone Configuration**
      * Sample Rate - determines the maximum frequency of the audio, how much data is used as well as how long the recorder will run.  Continuous runtimes in hours can be calculated as battery capacity in mAh/current.  The rated capacities are always best case at room temperature with a new cell.  If you want accurate runtimes, you may need to derate the capacity to account for cell age and temperature.  This could be anywhere from 0-25%.  Data usage and runtimes below assume continuous recordings with a 3500mAh battery at room temerature.  This is best case, which will often not be seen.  Standy/Off power consumption is negligible(0.3mA).
          |Sample Rate| Current| Data Usage per Day| Runtime|
          |----|-----|------|------|
          |8k| 3.3mA| 1.3GB| 1060h|
          |12k| 4.3mA| 1.9GB| 814h|
          |16k| 4.8mA| 2.6GB| 729h|
          |24k| 6.0mA| 3.9GB| 583h|
          |32k| 7.0mA| 5.1GB| 500h|
          |48k| 8.8mA| 7.7GB| 397h|
      * Gain - supports configurable output gain between 0dB and 40.5dB.  Higher gain values are generally useful, but can always be amplified in post processing.  Unless you're dealing with very loud sound sources, using high gain is beneficial.  With a 0dB gain, the maximum amplitude the recording system can handle is 120dB.  At 40.5dB gain, the maximum amplitude is 79.5dB
      * High Pass Filter - 0(Min) to 7(Max).  This reduces the amplitude of low frequency audio.  This can be useful to filter out low frequency noise and minor wind events.  Generally I would use the minium value unless you know how this works with your specific target species.  Post processes can always add a High Pass Filter.
    * **Location**
      - Recorder - shows the configured Lat/Long set on the recorder(location can be copied by long pressing)
      - Actual - shows the current Lat/Long from your mobile device(location can be copied by long pressing)
      - Separation - shows distance between the recorder configured position and your mobile devices location.  This can be useful to ensure the recorder's position closely matches your mobile device.
    * **Buttons**
      - Update - sends the current configuration to the recorder, including the date/time and location.
      - Use Defaults - sets all selections to the default configuration, this will be grayed out if it matches the default.

## Recorder File System
  - **audio**
    * All recordings will be stored in this directory.
    * All files follow this naming convention: <FILE_PREFIX>_<RECORDER_ID>_YYYY-MM-DD_THH-MM-SS.WAV
  - **Metadata**
    * <FILE_PREFIX>_<RECORDER_ID>meta.txt file that tracks a temperature log during recordings.
  - **Log**
    * <RECORDER_ID>log.txt log file for troubleshooting.  Tracks all updates to the configuration as well as when recordings start/stop or certain error conditions.
  - **Sites**
    * <RECORDER_ID>_sites.txt csv file that tracks the lat/lon for each site/prefix
  - **config.txt**
    * Configuration settings for the recorder, it is not recommended to manually modifify this.  The app automatically updates this file when making changes.


## How to Update the Firmware
  - Physical connections
    - https://ftdichip.com/products/ttl-232r-3v3/
    - Connect the cable to the board with the black wire to GND and the green wire to DTR.
  - Install Artemis firmware tool
    - https://github.com/sparkfun/Artemis-Firmware-Upload-GUI/releases
  - Download the latest firmware 
    - https://github.com/tgruetzm/Owl-Sense



## **FCC Compliance Statement**
### **Contains FCC ID: 2ASW8-ART3MIS**

CAUTION: The manufacturer is not responsible for any changes or modifications not expressly approved by the party responsible for compliance. Such modifications could void the user’s authority to operate the equipment.

NOTE: This equipment has been tested and found to comply with the limits for a Class B digital device, pursuant to part 15 of the FCC Rules. These limits are designed to provide reasonable protection against harmful interference in a residential installation. This equipment generates, uses, and can radiate radio frequency energy, and if not installed and used in accordance with the instructions, may cause harmful interference to radio communications. However, there is no guarantee that interference will not occur in a particular installation. If this equipment does cause harmful interference to radio or television reception, which can be determined by turning the equipment off and on, the user is encouraged to try to correct the interference by one or more of the following measures:
  - Reorient or relocate the receiving antenna.
  - Increase the separation between the equipment and receiver.
  - Connect the equipment into an outlet on a circuit different from that to which the receiver is connected.
  - Consult the dealer or an experienced radio/TV technician for help.


## **Supplier's Declaration of Conformity** 
### **47 CFR § 2.1077 Compliance Information**


  **Product Name:** Owl Sense  
  **Product Model:** v1.1  
  **Manufacturer:**  
  Owl Sense LLC  
  Lolo, MT 59847  
  troy@owlsense.co  
  www.owlsense.co  

  **Modular Components Used:**  
  NAME: Artemis V1  
  MODEL: Artemis V1  
  FCC ID: 2ASW8-ART3MIS  
  This device complies with part 15 of the FCC Rules. Operation is subject to the following two
  conditions: (1) This device may not cause harmful interference, and (2) this device must accept
  any interference received, including interference that may cause undesired operation.