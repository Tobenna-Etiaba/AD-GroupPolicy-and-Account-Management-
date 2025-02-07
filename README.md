<p align="center">
<img src="https://i.imgur.com/aMMGyHQ.jpeg" height="80%" width="80%" alt="Setting Up in Azure"/>
<br />

<h1>ActiveDirectory (Part 3 - Group Policy & Account Management)</h1>
I will be demonstrating how you can use group policy to disable accounts/users whenever they use a wrong password after a certain amount of times, as well as demonstrating how to re-enable those accounts and a bit more.

<h2>Walkthrough</h2>

- From within Server(the Windows Server VM) input gpmc.msc to open group policy management.

<img width="401" alt="Screenshot 2025-02-07 at 14 20 51" src="https://github.com/user-attachments/assets/589447e5-733c-464a-8823-d9808e4f9e32" />

- When group policy management policy is open right-click *Default Domain Policy* and click edit, then go to account policies, then click on account lockout policies and choose the settings you want.

<img width="753" alt="Screenshot 2025-02-07 at 14 21 09" src="https://github.com/user-attachments/assets/6cdd75c2-0640-47b4-831a-c710c00c19e2" />

<img width="775" alt="Screenshot 2025-02-07 at 14 21 48" src="https://github.com/user-attachments/assets/c74a0b4e-ba18-4407-ab6f-9a4f25661016" />

<img width="786" alt="Screenshot 2025-02-07 at 14 23 04" src="https://github.com/user-attachments/assets/0fa9936e-799a-4cdf-8610-f0fbfaacb4a4" />

<img width="788" alt="Screenshot 2025-02-07 at 14 23 57" src="https://github.com/user-attachments/assets/fabccf2b-aec3-4b8e-9583-77af6b4f5cf9" />

<img width="787" alt="Screenshot 2025-02-07 at 14 24 14" src="https://github.com/user-attachments/assets/a8212860-8562-452e-92ef-0bc319970e74" />

- Once that's done login to User(the Windows 10 VM), update the policy by typing *gpupdate /force* within powershell and then log out.

<img width="858" alt="Screenshot 2025-02-07 at 14 29 17" src="https://github.com/user-attachments/assets/b907a573-c470-4780-ab6e-0bb5cfa53ba7" />

- Attempt to log back into User with a wrong password multiple times.

<img width="1149" alt="Screenshot 2025-02-07 at 14 31 01" src="https://github.com/user-attachments/assets/403b4ba6-afbd-48cf-8e69-511ec0d25f9e" />

<img width="1151" alt="Screenshot 2025-02-07 at 14 31 22" src="https://github.com/user-attachments/assets/9e1a6355-9857-4e8e-8c31-b46a69a79fc5" />

- After multiple failed attempts the account you tried logging in with will be disabled. To re-enable it go to active directory users & computers and unlock the account (You can also change the password. The original password was password1).

<img width="754" alt="Screenshot 2025-02-07 at 14 32 01" src="https://github.com/user-attachments/assets/beb70149-7c37-4c5a-91ca-9edbbc5f22cc" />

<img width="1046" alt="Screenshot 2025-02-07 at 14 33 09" src="https://github.com/user-attachments/assets/58b4d4b7-8bcc-47e3-b50f-4f0ccdc70a2b" />

<img width="706" alt="Screenshot 2025-02-07 at 14 33 32" src="https://github.com/user-attachments/assets/2eeed32c-5284-4ba8-abfa-36b17f33aaae" />

<img width="1149" alt="Screenshot 2025-02-07 at 14 35 18" src="https://github.com/user-attachments/assets/aed04ee8-14c5-4966-a4e1-0736bde809cf" />

- To disable the account go back to active directory users & computers disable it.

<img width="516" alt="Screenshot 2025-02-07 at 14 36 13" src="https://github.com/user-attachments/assets/4f6a9fd8-27c6-47c5-bb44-30315e5a307d" />

<img width="517" alt="Screenshot 2025-02-07 at 14 36 25" src="https://github.com/user-attachments/assets/9c731668-3929-4bd4-aeef-b863b5a1adc9" />

<img width="1162" alt="Screenshot 2025-02-07 at 14 36 57" src="https://github.com/user-attachments/assets/6cbaaa90-d34e-4752-90b8-23a3022cc4b9" />

