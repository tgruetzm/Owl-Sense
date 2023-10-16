
<img src="logo.png" alt="Owl Sense" width="150" />

## Overview
  * Owl Sense offers an affordable and user-friendly audio recording solution for wildlife research.
  * Specifically built with extended runtimes and top-notch audio quality in mind.

## Quick Start Guide
  1. Install a protected 18650 battery and memory card.
  2. The Error LED will flash indicating the clock is not set, configuration may also be missing.
  3. Hold the Wireless button until the LED illuminates, to turn on the radio.
  4. Load the Owl Sense app on your phone.
  5. Connect to and configure the device and press Update.



## Hardware Overview
  - **Buttons**
    * Enable - enables or disables the recorder.  Hold the button until the record LED lights up, then release.
    * Wireless - turns on the wireless radio.  Hold until the blue wireless LED lights up, then release.
    * Reset - a single press will reset the board.  Do not reset when a recording is in progress.  This may corrupt the memory card.  The green standy LED will illuminate after the system loads.
  - **LED indicators**
    * No LED -  if no LED is illuminated the recorder is disabled.  No recordings will take place.
    * Record - red LED, indicates that a recording is in progress.  The LED blinks everytime a file write occurs.  At a 48k sample rate it's one write/blink per second, at 12k it's one write/blink per 4 seconds, etc...
    * Standy - green LED, indicates that the recorder is enable and is waiting for an active schedule.
    * Wireless - blue LED, solid indicates the wireless radio is powered.  Blinking indicates an active connection.
    * Error - red LED, blinking indicates an error.  Recordings will not happen if there is an error condition.  To see the exact error, use the Owl Sense app.
  - **Battery**
    * Only use protected 18650 cells from reputable manufacturers.
    * Nevery use a battery if it shows any signs of damage or leakage.
    * End user is responsible for any damage or injury caused by misuse or mishandling lithium ion batteries and chargers.
    * Lithium batteries should always be stored individually and in a case or box that separates cells.
    * Lithium batteries may explode, burn, or cause a fire if misused or mishandled.
  - **Memory Card**
    * At this time only Samsung EVO Plus 64GB or 128GB cards are supported.  Others will work, but there is not guarantee of compatability.  Other cards may significantly reduce runtimes.
  - **Microphone**
    * Featuring Infineon's [IM73D122](https://www.infineon.com/cms/en/product/sensor/mems-microphones/mems-microphones-for-consumer/im73d122/) microphone
    * Ultra-low self-noise/ultra-high SNR 73dB(A)
    * Microphones are user serviceable, in the event of failure or better microphones becoming available.
    * The Microphone element is protected externally by an IPx4 hydrophobic Gore membrane.  An external vent helps keep water out of the microphone and dramatically reduces down time from the element being saturated.  The microphone itself is internally rated as IP57.


## iOS App Overview
  - **Main Page**
    * Recorder List - shows an item for each recorder in range that has the wireless radio on.
    * Defaults - allows configuration of default values, these can be easily loaded to any recorder or are automatically loaded if no configuration file is found.
  - **Recorder Detail Page**
    * **Recorder Detail** - shows basic info about the recorder.
      - ID - this value is unique to each recorder.
      - Status - shows details for any error or OK.
      - Battery levels - shows voltage and approximate battery capacity remaining.
      - Current date/time - date/time set on the recorder.
      - dB level - shows approximate dB level of the microphone.
      - Card details - shows basic storage information.
      - Firmware version
    * **Recorder Configuration**
      - Enabled - identical function to the physical Enable button, enables or disables the recorder.
      - File Prefix - all audio files will be prefixed with this name.  Supports 18 characters, alphanumeric and dash.
      - Auto DST - Automatically adjusts the recorders clock when DST starts and ends.  Follows US DST standards.
      - Schedule
        1. Continuous
        2. Sunrise to Sunset, with a configurable extension period(0,30,60,90,120 minutes before and after)
        3. Sunset to Sunrise, with a configurable extension period(0,30,60,90,120 minutes before and after)
        4. Sunrise and Sunset, with a configurable extension period(30,60,90,120 minutes before and after)
        5. Duty Cycle, with a configurable On Period and Off Period in minutes.
      - Start Date - configurable date/time to delay before starting the schedule.  Green Standby LED will blink until the date/time passes.
      - File Splitting - 1, 2, 4, 6, 12 or 24 hour file splitting.  Files will automatically split at 4GB if exceeded.
    * **Microphone Configuration**
      * Sample Rate - determines the maximum frequency of the audio, how much data is used as well as how long the recorder will run.  Continuous runtimes in hours can be calculated as battery capacity in mAh/current.  The rated capacities are always best case at room temperature with a new cell.  If you want accurate runtimes, you may need to derate the capacity to account for cell age and temperature.  This could be anywhere from 0-20%.  Data usage and runtimes below assume continuous recordings with a 3500mAh battery.  This is absolute best case, which will rarely be seen.  Standy/Off power consumption is negligible(0.4mA).
        - Sample Rate, Current, Data Usage per Day, Runtime
        - 8k, 3.25mA, 1.3GB, 1077h
        - 12k, 4.25mA, 1.9GB, 823h
        - 16k, 4.75mA, 2.6GB, 736h
        - 24k, 6.15mA, 3.9GB, 569h
        - 32k, 7.00mA, 5.1GB, 500h
        - 48k, 11.5mA, 7.7GB, 300h
      * Gain - supports configurable output gain between 0dB and 40.5dB.  Higher gain values are generally useful, but can always be amplified in post processing.  With a 0dB gain, the maximum amplitude the recording system can handle is 120dB.  At 40.5dB gain, the maximum amplitude is 79.5dB
      * High Pass Filter - 0(Min) to 7(Max).  Generally I would use the minium value unless you know how this works with your specific target species.  Post processes can always add a High Pass Filter.
    * **Location**
      - Lattitude and Longitude currently set on the recorder.
    * **Buttons**
      - Update - sends the current configuration to the recorder, including the date/time and location.
      - Use Defaults - sets all selections to the default configuration, this will be grayed out if it matches the default.

## Recorder File System
  - **audio**
    * All recordings will be stored in this directory.
    * All files follow this naming convention: <FILE_PREFIX>_<RECORDER_ID>_YYYY-MM-DD_THH-MM-SS.WAV
  - **Metadata**
    * <FILE_PREFIX>_<RECORDER_ID>meta.txt file that tracks the location and a temperature log.
  - **Log**
    * <FILE_PREFIX>_<RECORDER_ID>log.txt log file for troubleshooting.  Tracks all updates to the configuration as well as when recordings start/stop or certain error conditions.
  - **config.txt**
    * Configuration settings for the recorder, it is not recommended to manually modifify this.  The app automatically updates this file when making changes.



## How to Update the Firmware
  - Install Drivers
    - https://ftdichip.com/drivers/vcp-drivers/
  - Install Artemis firmware tool
    - https://github.com/sparkfun/Artemis-Firmware-Upload-GUI/releases
  - TODO

