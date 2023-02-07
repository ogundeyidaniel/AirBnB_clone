               THE Airbnb Project Clone
Steps
1)	Planning
2)	Analysis (Requirements)
3)	Design
4)	Implementation (Actual building of software)
5)	Testing
6)	Maintenance
======================================================================================================

Implementation Phase
Web App: 
Front-end design (use a console to rep front end using cmd module)
Back-end design (Use OOP concepts, classes, methods and attributes, inheritance, and polymorphism)
Database (file storage use json module)
Testing-> unittest module
======================================================================================================
.
               Analysis Phase (Airbnb)
               ----------------------
User account-> filed name, email, unique_id, created_date, updated_dated.
Reviews-> unique_id
Place
Amenity-> classes (attributes and methods), quantity
CRUD ( 4 actions in building web application)
C= Create
R= Read
U= Update
D= Delete/ Destroy
======================================================================================================
                Start of Airbnb Project
                -----------------------
                        Back-end
Class BaseModel()
-Defined attributes that are common
-Defined methods that are common
               class User (Base model):
-Inherit all the base class attributes
-Inherit all the base class methods
There are some unique attributes that can’t be inherited from another class.
-Declare all unique attributes of this class
-Declare all unique methods of this class
              Class Amenity (BaseModel):
-Attributes
======================================================================================================
                       Storage
Everything is Python is an OBJECT
Prepare this object for storage-> converting python object into json format is called serialization (that is to store and retrieve anytime) and vice versa is called deserialization.
Class fileStorage ():
-Managing the attributes related to the file
-Managing the method related to the file
How to link the classes
Class BaseModel ():
Def save(self):
      -save an instance of the class into the file
      -The attributes are id, created_ at, updated_at (using the module datetime)
Storage.save(self)
Class fileStorage ():
__init__py
From filestorage import fileStorage
Storage = fileStorage
-a module is a python script that can be imported and used in another python script.
-A package is a collection of modules in a giving directory __int__py	
Front-end
Console Application
Using cmd module
Create user
Update user 09473rhrh094 “first_name” “Ako”
Commands-> create | show | count | destroy | update | list  
How to do all this we import
==================================================================================================
Create a class
Class MyConsole(cmd.Cmd):
	Import cmd (eg ./Airbnb file call by it name not module)
	If _name_= = ’_main_’:
	Myconsole().cmdloop()


Class MyConsole(cmd.Cmd):
    Pass
Prompt = “<<<<” ( it can be modified to run on command line
-You can add whatever in the console
def do_create(self, line):
      print (“ I love to”, line)
def do_EOF(self, line):
       return True
If _name_ == “_main_”:
MyConsole().cmdloop()
The above command runs the cmd console as ./MyConsole.py
This website helps more about cmd console https://pymotw.com/3/cmd
==================================================================================================
                      In here there will be several files that allow the program to work.
/console.py : The main executable of the project, the command interpreter.

models/engine/file_storage.py: Class that serializes instances to a JSON file and deserializes JSON file to instances

models/__ init __.py: A unique FileStorage instance for the application

models/base_model.py: Class that defines all common attributes/methods for other classes.

models/user.py: User class that inherits from BaseModel

models/state.py: State class that inherits from BaseModel

models/city.py: City class that inherits from BaseModel

models/amenity.py: Amenity class that inherits from BaseModel

models/place.py: Place class that inherits from BaseModel

models/review.py: Review class that inherits from BaseModel
==================================================================================================
                            How to use it
                            -------------
It can work in two different modes:

Interactive and Non-interactive.

In Interactive mode, the console will display a prompt (hbnb) indicating that the user can write and execute a command. After the command is run, the prompt will appear again a wait for a new command. This can go indefinitely as long as the user does not exit the program
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):

EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
====================================================================================================
In Non-interactive mode, the shell will need to be run with a command input piped into its execution so that the command is run as soon as the Shell starts. In this mode no prompt will appear, and no further input will be expected from the user.In Non-interactive mode, the shell will need to be run with a command input piped into its execution so that the command$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$

                                           Format of Command Input
                                           -----------------------
In order to give commands to the console, these will need to be piped through an echo in case of Non-interactive mode.

In Interactive Mode the commands will need to be written with a keyboard when the prompt appears and will be recognized when an enter key is pressed (new line). As soon as this happens, the console will attempt to execute the command through several means or will show an error message if the command didn't run successfully. In this mode, the console can be exited using the CTRL + D combination, CTRL + C, or the command quit or EOF.
======================================================================================================================================
                                            Arguments
                                            ---------
Most commands have several options or arguments that can be used when executing the program. In order for the Shell to recognize those parameters, the user must separate everything with spaces.

Example:

user@ubuntu:~/AirBnB$ ./console.py
(hbnb) create BaseModel
49faff9a-6318-451f-87b6-910505c55907
user@ubuntu:~/AirBnB$ ./console.py

user@ubuntu:~/AirBnB$ ./console.py $ echo "create BaseModel" | ./console.py
(hbnb)
e37ebcd3-f8e1-4c1f-8095-7a019070b1fa
(hbnb)

user@ubuntu:~/AirBnB$ ./console.py
=====================================================================================================================================
                                          Available commands and what they do
                                          -----------------------------------
The recognizable commands by the interpreter are the following:

Command	Description
quit or EO:	     Exits the program
Usage:	             By itself
-----	             -----
help:	             Provides a text describing how to use a command.
Usage:	             By itself --or-- help <command>
-----	             -----
create	Creates a new instance of a valid Class, saves it (to the JSON file) and prints the id. Valid classes are: BaseModel, User, State, City, Amenity, Place, Review.
Usage:              create <class name>
-----	            -----
show:	            Prints the string representation of an instance based on the class name and id
Usage:   	    show <class name> <id> --or-- <class name>.show(<id>)
-----	            -----
destroy	Deletes an instance based on the class name and id (saves the change into a JSON file).
Usage	destroy <class name> <id> --or-- .destroy()
-----	-----
all	Prints all string representation of all instances based or not on the class name.
Usage	By itself or all <class name> --or-- <class name>.all()
-----	-----
update	Updates an instance based on the class name and id by adding or updating attribute (saves the changes into a JSON file).
Usage	update <class name> <id> <attribute name> "<attribute value>" ---or--- <class name>.update(<id>, <attribute name>, <attribute value>) --or-- <class name>.update(<id>, <dictionary representation>)
-----	-----
count	Retrieve the number of instances of a class.
Usage	<class name>.count()
======================================================================================================================================
                                           Authors
Ako Atem Sampson
Daniel Ogundey
