# roborock-automation
This repository contains a collection of scripts that allow you to automate Roborock vacuum cleaner cleaning tasks when family members are not at home.
Those script have been tested with Roborock s5.

## Features
- Schedule cleaning sessions at specified times using cron job, when meeting conditions.
- Check the status of the vacuum cleaner, including battery level and current state.
- Initiate cleaning sessions.
- Support for multiple Roborock devices connected to your network.

## Prerequisites

- Python 3.x installed on your system.
- The `pip` package manager.
- Access to the `cron` utility to schedule tasks.
- device ip and token

## Installation

1. Clone this repository to your desired location:

	```shell
	git clone git@github.com:Marcwe25/roborock-automation.git
	cd roborock-automation
	```
2. Configure the IP addresses of family members' devices:
   
	Open the ipList file and replace the sample IP addresses with the actual IP addresses of family members' devices, each on a separate line. These IP addresses are used to determine if any family members are connected and trigger the cleaning accordingly.

3. Modify the cron job expression in the roborock_automation_install.sh script to adjust the schedule according to your preferences.

4. Running the Installation Script
	The installation script sets up the necessary cron jobs for automated scheduling.
Run the following command:
	```shell
	./roborock_automation_install.sh
	```

Note: The installation script requires appropriate permissions to modify the crontab.

#### Usage

##  Manual Cleaning
manually start a cleaning session, run the following command:
```shell
./mirobo_command.sh start_clean
```
To check the current status of the Roborock device, including battery level and state, run:
```shell
./mirobo_command.sh get_info
```

####  Automatic Cleaning
The mirobo_script.sh script evaluates various conditions before initiating an automatic cleaning session.
Modify the conditions as needed for your use case, particularly the check_ip_presence function to customize the behavior based on member connectivity.

####  Scheduled Cleaning
The mirobo_script.sh script is scheduled to run automatically at specific times using cron jobs. By default, it runs every minute from 8 AM to 7 PM, subject to the conditions specified in the script. Modify the cron job expression to adjust the schedule according to your preferences.

####  Troubleshooting
If the scripts fail to run or produce errors, make sure you have the necessary permissions to execute them and that all dependencies are installed correctly.
Verify that the IP addresses listed in the ipList file correspond to the actual IP addresses of family members' devices.
