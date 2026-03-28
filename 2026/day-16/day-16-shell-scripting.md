Task 1 : My First Script
create a script file hello.sh (.sh) extension
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/49894bac-77bd-4a0f-839c-999305ba8dbc" />

Add the shebang line #!/bin/bash at the top

Print Hello, DevOps! using echo
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/7b30dac2-a65a-42ab-a1b8-e34e16592da9" />

Make it executable
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/d9686363-d195-44f0-b1f6-374a1a49fdf9" />

Run the script file
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/db61d7cc-149c-448e-9884-086076735ca0" />

 What happens if you remove the shebang line?
 it still execute the script file

 Task 2 : Create variables.sh with:
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/ec175ff3-42e2-4ee9-8bb4-01c29588f734" />

A variable for your NAME
A variable for your ROLE (e.g., "DevOps Engineer")

Print: Hello, I am <NAME> and I am a <ROLE>
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/6650ec02-08b2-42cf-bd94-89b711fabd5c" />

Try using single quotes vs double quotes — what's the difference?
single quotes doesn't worked

Task 3: User Input with read
Create greet.sh that:
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/95e15aaf-6277-40ae-b788-a6ec87582d85" />

Asks the user for their name using read
Asks for their favourite tool
Prints: Hello <name>, your favourite tool is <tool>
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/fb299335-c854-42ae-b5d0-2b3e53fca139" />


Task 4: If-Else Conditions
Create check_number.sh that:

Takes a number using read
Prints whether it is positive, negative, or zero
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/a073f1c5-ee61-4eaa-ba14-c558b1a66846" />

<img width="1026" height="233" alt="image" src="https://github.com/user-attachments/assets/fd372dbd-8e93-45e5-8851-d44dd9e09ea9" />

Create file_check.sh that:

Asks for a filename
Checks if the file exists using -f
Prints appropriate message
<img width="1026" height="313" alt="image" src="https://github.com/user-attachments/assets/c48c848b-6e5a-40cb-bdd2-e25a7e3ffe06" />
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/752f45e2-0c2a-462d-8e31-4f8be05284d6" />

Task 5: Combine It All
Create server_check.sh that:

Stores a service name in a variable (e.g., nginx, sshd)
Asks the user: "Do you want to check the status? (y/n)"
If y — runs systemctl status <service> and prints whether it's active or not
If n — prints "Skipped."
Script:
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/10015888-b19e-4f5a-8430-cc7b330a203a" />

<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/b63a0992-84ee-41c1-87e2-e7c7840bb084" />
<img width="1026" height="312" alt="image" src="https://github.com/user-attachments/assets/c100e6b6-042f-45fe-a977-be43f1e74453" />

