# Correct usage of sfc /SCANNOW

On Windows 10, the deployment image service and management (DISM) tool is intended for administrators to prepare, modify, and repair systems, including Wi.

On Windows 10, the deployment image service and management (DISM) tool is intended for administrators to prepare, modify, and repair systems, including the Windows Recovery Environment, Windows Installation, and Windows PE (WinPE). It can also be used in conjunction with local recovery images to fix system issues.

The System File Checker (SFC) tool can replace lost or corrupted system files with recovery images. The only caveat is that if one or more system files are damaged in a local image, the SFC command will not work. DISM and an "install.wim" image file can be used to repair the image, then use the SFC tool to repair the installation without having to reinstall the operating system.

How to use DISM to repair the Windows 10 image

The Dism command tool includes three options: CheckHealth, ScanHealth, and RestoreHealth. We usually need to use them in sequence. The RestoreHealth option can use different source files.

DISM command's CheckHealth option

CheckHealth option is used to determine any corruption in the Windows 10 local image, but does not perform any type of repair.

Enter the following command in the command prompt:

DISM /Online /Cleanup-Image /CheckHealth

The Dism tool will run and verify any data corruptions that may need to be repaired in the local image.

DISM command's ScanHealth option

ScanHealth option performs a more advanced scan to determine if the image has any issues.

Enter the following command in the command prompt:

DISM /Online /Cleanup-Image /ScanHealth

After completing these steps, scanning may take some time to check if the image needs any repairs.

RestoreHealth option of the DISM command

If there are issues with the system image, use DISM with the RestoreHealth option to automatically scan and fix common problems.

Enter the following command in the command prompt:

DISM /Online /Cleanup-Image /RestoreHealth

Note: If the command hangs, this is normal.

After completing these steps, if necessary, DISM will connect to the Windows server to download and replace corrupted files. Therefore, the repair steps are as follows:

(1) Use winver to check the version of your operating system and download the corresponding official ISO clean system image file.

(2) Open or unzip the image, use the command

DISM /Online /Cleanup-image /RestoreHealth /Source:D:\Sources\install.vim

How to run SFC to fix issues on WINDOWS 10

The previous steps were aimed at fixing issues with the system image, not with Windows 10. After restoring the image to normal status, you can use the System File Checker (SFC) command tool to repair the current settings of Windows 10.

Enter the following command in the command prompt:

SFC /scannow

Note: If errors are found, you may need to run the command approximately three times to ensure all content has been correctly fixed.

After completing these steps, the System File Checker tool will use the local image file to repair system files. The log files will be saved in "%windir%/Logs/CBS/CBS.log" and "%windir%\Logs\DISM\dism.log". You can review these files for more details about the process.


## Payment

Here is a pay link on Stripe ( https://buy.stripe.com/3cs8yP7sY87d0vu9AB ). Please contact me lonlonago@foxmail.com after funding $89, and I will send you a complete data files , thank you!

![111.png](111.png)
