# Backing-up-data-in-windows-and-Linux-
In this project I will create files and directories on the Linux virtual machine. Next,  will back up and restore those resources by using the tar command. Finally,  will install Windows Server Backup, and then I will back up and restore resources by using Windows Server Backup.

In this project we are making use of  Windows server(DC) + Ubuntu 24.04.2 

Using the root acc, we are going to create 4 directories name DirA, DirB, Backup and restore 

<img width="721" height="481" alt="image" src="https://github.com/user-attachments/assets/c9fd17cb-18dc-4ebb-bfde-d41bc5ee74ca" />

Then we are going to create file20, file30, and file40 in DirA  
<img width="1057" height="85" alt="image" src="https://github.com/user-attachments/assets/f4d2dcab-fd5b-439a-a38d-632ca51fcd26" />
<img width="335" height="191" alt="image" src="https://github.com/user-attachments/assets/6b5b5719-ddf3-4508-8f05-4c240bef2f02" />


 Create file50 in /DirB
 <img width="508" height="148" alt="image" src="https://github.com/user-attachments/assets/e979660a-5cb7-4511-bd27-3a4116fb3e22" />

 In the next phase of this exercise we are going to  Back up data using the tar command

 Back up /DirA and all of its contents to a file named /Backup/backup.tar by using the tar command.
 <img width="853" height="56" alt="image" src="https://github.com/user-attachments/assets/89a0f93e-f741-4fe8-b099-5a2304285d88" />
 <img width="302" height="60" alt="image" src="https://github.com/user-attachments/assets/0aed99a5-b70f-4fe6-acb6-0dca7b221d82" />

 Append /DirB/file50 to the backup.tar backup job.
 <img width="839" height="47" alt="image" src="https://github.com/user-attachments/assets/7e8037c3-d19a-438e-934b-622d9921a82d" />

 Verify the contents of backup.tar
 <img width="520" height="139" alt="image" src="https://github.com/user-attachments/assets/22a9d847-dde4-4947-87b7-22a10fafe5bf" />

 Back up and compress /DirA to /Backup/backup2.tar.gz
 <img width="740" height="56" alt="image" src="https://github.com/user-attachments/assets/e700e5b9-faa2-420f-81f5-07f4fad49919" />

 Change to the root directory and delete /DirA and all its contents
 <img width="830" height="120" alt="image" src="https://github.com/user-attachments/assets/feb8449d-6c60-4191-a3fa-bd0347360fba" />
 <img width="935" height="111" alt="image" src="https://github.com/user-attachments/assets/dc772dcc-61d9-4bf3-a23d-4c311c4befd2" />

Note: As we can see on recent screenshot that DirA is no longer on our list 

Change to the /Restore directory, and then restore DirA and all of its contents from the backup2.tar.gz file to the /Restore directory.
<img width="603" height="84" alt="image" src="https://github.com/user-attachments/assets/6aeed9f8-7ae6-4c08-b787-8d7df8805cdb" />

Display the contents of the /Restore directory
<img width="457" height="79" alt="image" src="https://github.com/user-attachments/assets/fdbd632f-a0cc-479f-859a-16c153cd4e86" />

In the next Phase we are going to switch to our Windows server machine using credentials Hexelo\Administrator 
<img width="940" height="895" alt="image" src="https://github.com/user-attachments/assets/4cfb8f58-6d5b-4ad0-ad6b-99a21209aa8d" />

In Powershell Create two folders named Restore and Data on drive C, and then create two files named file1.txt and file2.txt in C:\Data.
<img width="600" height="364" alt="image" src="https://github.com/user-attachments/assets/381036be-d73c-4e2a-b5e3-cebc63badd6e" />

Create file1.txt and file2.txt in C:\Data
<img width="772" height="302" alt="image" src="https://github.com/user-attachments/assets/ab81176b-8f2a-4c15-8471-6a62c43a4134" />

On the next phase we are going to Back up data by using Windows Server Backup

lets install Window server backup 
<img width="875" height="691" alt="image" src="https://github.com/user-attachments/assets/03d8a5a4-fec7-4bb5-9f5c-f461a4729606" />

We are going to Navigate to tools and find Windows server backup and then click on local Backup 
Then on the right side of the page we are going to click Backup once, A wizard should pop out 
On the Backup Options page, select Different options and click Next.
On the Select Backup Configuration page, choose Custom and click Next.
On the Select Items for Backup page, click the Add Items button.
 Expand Local Disk (C:), check the box for the Data folder, and click OK. Click Next.
 <img width="816" height="538" alt="image" src="https://github.com/user-attachments/assets/a484cf60-b60b-4f65-83c8-a2149bd5294c" />

 On the Specify Destination Type page, select Local drives and click Next.
On the Select Backup Destination page, use the dropdown menu to choose your D: drive volume, then click Next.
<img width="879" height="637" alt="image" src="https://github.com/user-attachments/assets/02b64de4-da0a-45a7-8942-b9f47fb047a1" />

Review your settings on the Confirmation page and click Backup.
<img width="923" height="805" alt="image" src="https://github.com/user-attachments/assets/a6d398a6-51af-4de9-9ab1-250e23b1582a" />

 Once the status shows "Completed", click Close.

 In the Next Phase we are going to Delete C:\Data by using File Explorer.
 <img width="738" height="375" alt="image" src="https://github.com/user-attachments/assets/324e3fa4-4179-469a-bfd5-d3d1edb70955" />
 <img width="732" height="345" alt="image" src="https://github.com/user-attachments/assets/58dc9927-fadf-4d39-8c60-f4c4a2f915a6" />

Open Server Manager, click Tools in the top-right corner, and select Windows Server Backup.
 In the right-hand Actions pane, click Recover... to open the Recovery Wizard
 <img width="835" height="575" alt="image" src="https://github.com/user-attachments/assets/6f90fb2f-3fdd-4e43-8ca9-845fcc3a1d7e" />

On the Getting Started page, select This server (DC1) and click Next.
 On the Select Backup Date page, select the date and time of the backup you just made, then click Next.
 On the Select Recovery Type page, choose Files and folders and click Next.
On the Select Items to Recover page, expand DC1 -> C: in the left pane, click on the Data folder so its contents (file1.txt, file2.txt) appear on the right, and click Next.
<img width="925" height="623" alt="image" src="https://github.com/user-attachments/assets/642a3f46-c91a-4ebd-840b-f70c6393c3dc" />

On the Specify Recovery Options page, under Recovery destination, select Another location.
Click Browse..., navigate to and select C:\Restore, and click OK. Click Next.
<img width="863" height="483" alt="image" src="https://github.com/user-attachments/assets/9b9eece4-a6e4-4748-b331-b063a955c34c" />

Review the summary on the Confirmation page and click Recover. Once the status says "Completed", click Close.
<img width="879" height="616" alt="image" src="https://github.com/user-attachments/assets/028fa1ad-cb7d-401c-8eca-9a64f8db4f4d" />

Display the contents of the C:\Restore folder to verify that you recovered the contents of the Data folder.

<img width="847" height="534" alt="image" src="https://github.com/user-attachments/assets/3dc52108-5c94-43aa-adc0-7351926c6a9a" />





 


 


 














 



 




 






