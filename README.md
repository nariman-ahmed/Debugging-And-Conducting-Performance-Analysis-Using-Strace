# 1) Debugging a Buggy App Using Strace

### Using the command strace ./syscall_buggyApp.exe will output the folllowing in the terminal:

![Screenshot 2025-03-16 160554](https://github.com/user-attachments/assets/59495a03-c231-4639-8a01-aaabb4963f62)
![Screenshot 2025-03-16 160603](https://github.com/user-attachments/assets/f65fa0f1-900d-478a-bc22-e309b60fd9f7)

### *We can see that there has been a failed system call request at "access" and "openat"*

### *Access is used when the programm is trying to access a certain file from the file system stack, as we can see from its documentation, it takes the file pathname as an argument and if the file doesn't exist it will faile to access it.*

![Screenshot 2025-03-16 155137](https://github.com/user-attachments/assets/172de20f-76f4-4019-b13e-7092a33d30c6)

![Screenshot 2025-03-16 155159](https://github.com/user-attachments/assets/30a0e1f7-1b88-4307-8365-f1d7bbe47a89)

![Screenshot 2025-03-16 160131](https://github.com/user-attachments/assets/e3b0be3c-4a3c-472c-b29d-2e24946e47b3)

### *Similarly, openat is a system call sent whan the program is trying to open a certain file. Like access, the program passes to it the pathname and if the file doesn't exist, openat will fail.*

![Screenshot 2025-03-16 155349](https://github.com/user-attachments/assets/ec083fdc-2262-4050-a589-c0e1e9e5ac55)

![Screenshot 2025-03-16 155330](https://github.com/user-attachments/assets/3c3b3a17-f7e4-4bff-a71d-f8fc3e1ad25e)

### *It also tries to access the file system stack:*

![Screenshot 2025-03-16 160719](https://github.com/user-attachments/assets/00dd5e2b-5173-4d1b-a05c-2e8bb32fc51d)

---

# 2) Performance Analysis:

### Using command ``` strace -c {command} -a ``` to get a table with the details of number and execution time of each syscall
ex for command ls:
![Screenshot 2025-03-17 034713](https://github.com/user-attachments/assets/bb278c0f-a68e-4221-a0da-66c7461fd0bf)

### Using command ``` time {command} ``` to find the total execution time for this command
![Screenshot 2025-03-17 035250](https://github.com/user-attachments/assets/c9b905a0-5c5a-4620-bae6-187734a59f30)

### A detailed analysis is shown in the pdf uploaded.
