# Day 17 – Shell Scripting: Loops, Arguments & Error Handling

## Task
Level up your scripting — use loops, handle arguments, and deal with errors.

You will:
- Write **for** and **while** loops
- Use **command-line arguments** (`$1`, `$2`, `$#`, `$@`)
- Install packages via script
- Add basic **error handling**

---

## Challenge Tasks

### Task 1: For Loop
1. Create `for_loop.sh` that:
   - Loops through a list of 5 fruits and prints each one
<img width="1291" height="267" alt="image" src="https://github.com/user-attachments/assets/7d153eab-fb87-49ec-9b72-3022ce1b80b8" />
<img width="1291" height="147" alt="image" src="https://github.com/user-attachments/assets/e6850da2-afdd-4d28-bd34-4b3c092660c4" />


2. Create `count.sh` that:
   - Prints numbers 1 to 10 using a for loop
<img width="1291" height="167" alt="image" src="https://github.com/user-attachments/assets/aa440567-aa66-472b-aba1-861dae9171aa" />
<img width="1291" height="261" alt="image" src="https://github.com/user-attachments/assets/9cd6cd71-742e-4a61-a5f0-153d20b4cffa" />

---

### Task 2: While Loop
1. Create `countdown.sh` that:
   - Takes a number from the user
   - Counts down to 0 using a while loop
   - Prints "Done!" at the end
<img width="1291" height="267" alt="image" src="https://github.com/user-attachments/assets/81d7c536-455b-4964-9034-8d0c7db1281a" />
<img width="1291" height="309" alt="image" src="https://github.com/user-attachments/assets/2317489f-8b98-4a3e-a4e3-2d7f95677f40" />

---

### Task 3: Command-Line Arguments
1. Create `greet.sh` that:
   - Accepts a name as `$1`
   - Prints `Hello, <name>!`
   - If no argument is passed, prints "Usage: ./greet.sh <name>"
<img width="1291" height="175" alt="image" src="https://github.com/user-attachments/assets/7426c5d1-d7d6-49ae-9110-ebac45407e96" />
<img width="1291" height="101" alt="image" src="https://github.com/user-attachments/assets/2df0b128-ede8-49d7-880c-25dc4ade6b5c" />


2. Create `args_demo.sh` that:
   - Prints total number of arguments (`$#`)
   - Prints all arguments (`$@`)
   - Prints the script name (`$0`)
<img width="1291" height="141" alt="image" src="https://github.com/user-attachments/assets/2d8eed63-c382-474e-aeab-1e15129a9e52" />
<img width="1291" height="101" alt="image" src="https://github.com/user-attachments/assets/a9d95e7d-099b-4bab-9ba7-f77e44644084" />

---

### Task 4: Install Packages via Script
1. Create `install_packages.sh` that:
   - Defines a list of packages: `nginx`, `curl`, `wget`
   - Loops through the list
   - Checks if each package is installed (use `dpkg -s` or `rpm -q`)
   - Installs it if missing, skips if already present
   - Prints status for each package
<img width="1291" height="487" alt="image" src="https://github.com/user-attachments/assets/e46671dc-2f4c-4c0d-ba96-d604febb0c02" />
<img width="1291" height="284" alt="image" src="https://github.com/user-attachments/assets/a7b8ed58-5844-4035-9572-d96d0311eed1" />

> Run as root: `sudo -i` or `sudo su`

---

### Task 5: Error Handling
1. Create `safe_script.sh` that:
   - Uses `set -e` at the top (exit on error)
   - Tries to create a directory `/tmp/devops-test`
   - Tries to navigate into it
   - Creates a file inside
   - Uses `||` operator to print an error if any step fails
<img width="1291" height="441" alt="image" src="https://github.com/user-attachments/assets/5fd4f02c-5a12-4bae-9c73-627135431cb0" />
<img width="1291" height="58" alt="image" src="https://github.com/user-attachments/assets/2b95d02b-4d82-4c8c-8f69-023ccb668019" />
