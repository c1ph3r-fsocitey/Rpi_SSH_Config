# Raspberry Pi SSH Configuration Files

## Step 1
Download the Kali Linux OS for Raspberry pi from their official site: 
https://www.kali.org/get-kali/#kali-arm

## Step 2

To configure Kali Linux on a Raspberry Pi 4 to connect to Wi-Fi on boot and enable SSH, you need to create two files in the boot partition of the SD card. Here are the steps:

1. Insert the SD card into your computer.
2. Locate the boot partition of the SD card. It should be accessible on your computer.
3. In the boot partition, create an empty file named `ssh` (without any extension). This file tells Kali Linux to enable SSH on boot.
4. Create a file named `wpa_supplicant.conf` in the boot partition. This file will contain the Wi-Fi network configuration.
5. Open `wpa_supplicant.conf` in a text editor and enter the following configuration (better if you copy and paste the following configuration in the file):

```
country=YOUR_COUNTRY_CODE
network={
    ssid="YOUR_NETWORK_NAME"
    psk="YOUR_NETWORK_PASSWORD"
}
```

Replace `YOUR_COUNTRY_CODE` with the 2-letter country code where you are located (e.g., US, GB, CA, etc.). Modify `YOUR_NETWORK_NAME` with the name (SSID) of your Wi-Fi network, and `YOUR_NETWORK_PASSWORD` with the password for your Wi-Fi network.

6. Save the `wpa_supplicant.conf` file and eject the SD card from your computer.
7. Insert the SD card into the Raspberry Pi 4 and power it on.
8. The Raspberry Pi should now connect to the specified Wi-Fi network on boot and enable SSH.

You should be able to SSH into the Raspberry Pi using its IP address. Remember to use the default credentials (`pi` as the username and `raspberry` as the password) unless you have changed them.

Note: Make sure the `wpa_supplicant.conf` file is properly formatted and does not contain any leading spaces or additional characters that can cause issues.

## Step 3

To SSH into a Raspberry Pi using Juice SSH on your Android device, follow these steps:

1. Ensure that your Raspberry Pi is connected to the same network as your Android device.
2. Install the Juice SSH app from the Google Play Store if you haven't already.
3. Launch Juice SSH on your Android device.
4. Tap on the "+" button to create a new connection.
5. In the "Name" field, enter a name for your Raspberry Pi connection (e.g., "Raspberry Pi SSH").
6. In the "Hostname" field, enter the IP address of your Raspberry Pi. You can find the IP address by running the `hostname -I` command on your Raspberry Pi or checking your router's connected devices list.
7. Specify the port number for SSH. The default SSH port is 22, but if you have changed it, enter the appropriate port number.
8. Choose the authentication method:
   - If using a password:
     - Enter your Raspberry Pi username (default is "pi") in the "Username" field.
     - Enter your Raspberry Pi password in the "Password" field.
   - If using key-based authentication:
     - Tap on "Use SSH key" and follow the on-screen instructions to import your private key.
9. Optionally, you can configure additional settings like terminal font size, color scheme, etc.
10. Tap on the "Save" button to save the connection.
11. Now, you should see your Raspberry Pi connection listed in the Juice SSH app.
12. Tap on your Raspberry Pi connection to establish the SSH connection.
13. If the login is successful, you will be connected to your Raspberry Pi via SSH using Juice SSH on your Android device.

You can now use the Juice SSH terminal interface to execute commands and interact with your Raspberry Pi remotely. Remember to use the correct username and password or SSH key for authentication.

Note: Ensure that SSH is enabled on your Raspberry Pi before attempting to SSH into it using Juice SSH.
