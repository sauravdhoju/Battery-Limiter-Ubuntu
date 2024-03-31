
# Battery Charge Threshold Setter


This script helps in setting the battery charge threshold for your Linux system. It adjusts the charge control end threshold for the battery to improve its longevity and health.

## Usage

Follow these steps to configure the battery charge threshold:

### Step 1: Check the Location

Before proceeding, ensure the correct location for your battery charge control settings. You can verify it by running the following command in the terminal:

```bash
echo 60 | sudo tee /sys/class/power_supply/BAT1/charge_control_end_threshold
```

Replace `BAT1` with the appropriate battery identifier if needed.

### Step 2: Edit the Crontab

Open the crontab file for editing using your preferred text editor. In this example, we'll use `gedit`:

```bash
sudo gedit /etc/crontab
```

### Step 3: Add Cron Job

Add the following line to the crontab file. This line ensures that the battery charge threshold is set to 60 at every system reboot:

```bash
@reboot root echo 60 > /sys/class/power_supply/BAT1/charge_control_end_threshold
```

Replace `BAT1` with the correct battery identifier if necessary.

### Save and Exit

Save the changes made to the crontab file and exit the text editor.

## Note

Ensure that you have the necessary permissions to modify system files and execute commands with root privileges.

## Disclaimer

This script is provided as-is without any warranty. Use it at your own risk.

# 
Saurav Dhoju



