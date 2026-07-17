A better version of Approach 3

Instead of a string, use a collection of valid choices.

accepted_numbers = ["1", "2", "3", "4"]

if chosen_option not in accepted_numbers:

or even better,

accepted_numbers = {"1", "2", "3", "4"}

if chosen_option not in accepted_numbers:

A set ({}) is designed for membership testing.



What is bytecode?

Think of it as:

A simpler, lower-level version of Python instructions that the Python Virtual Machine can understand


It is not human-readable.

It is not machine code either.

It sits in between.



Why does Python use bytecode?

Imagine reading a book written in French.

If you read it every day, would you translate every sentence from scratch every morning?

Probably not.

You would translate it once and keep the translated version.

Python does something similar.

Instead of translating your .py file every time, it stores the translated version as:



The next time you run your program, Python can often use that compiled version, making startup faster.

Who understands bytecode?

Not the CPU.

The Python Virtual Machine (PVM) understands bytecode.

Think of it as a translator:

Bytecode
    │
    ▼
Python Virtual Machine
    │
    ▼
Machine instructions
    │
    ▼
CPU


Does every programming language use bytecode?

No.

Different languages take different approaches.

Python → Source Code → Bytecode → Python Virtual Machine → CPU
Java → Source Code → Bytecode → Java Virtual Machine (JVM) → CPU
Go → Source Code → Machine Code → CPU
C → Source Code → Machine Code → CPU

So bytecode is one possible design, not a requirement for every language.


Earlier, we said Python creates a .pyc file to make future runs faster. That's true, but the .pyc file specifically contains Python bytecode—instructions for the Python Virtual Machine, not instructions that the CPU can execute directly.



docker build -t expense-tracker .



## Docker Commands Learned Today
## Command	What it does (Simple Explanation)

docker build -t contact_tracker .	Builds a Docker image from the current folder. -t gives the image a name. The . means "use the current folder."
docker images	                    Shows all Docker images stored on your computer.
docker run -it contact_tracker	    Creates and starts a container from the image. -i keeps keyboard input open and -t gives you a terminal.
docker ps -a	                    Shows every container (both running and stopped).
docker rm <container_id>	        Deletes a specific container.
docker container prune	            Deletes all stopped containers after asking for confirmation.
docker rmi contact_tracker	        Deletes the Docker image named contact_tracker.
docker rmi -f contact_tracker	    Force deletes the image, even if Docker would normally prevent it.
docker run -dit --name mycontacts contact_tracker	Runs a container in the background (-d), keeps it interactive (-it), and names it mycontacts.
docker exec -it mycontacts cat /app/contact.json	Runs a command inside a running container. Here, it displays the contents of contact.json.
docker cp testcontainer:/app/contact.json .	        Copies contact.json from the container to your current folder. The final . means "copy it here."
ls	                                                Lists all files and folders in the current directory.
ls -l	                                            Lists files with extra details such as permissions, size, owner, and modification date.
cat contact.json	                                Displays the contents of contact.json in the terminal.