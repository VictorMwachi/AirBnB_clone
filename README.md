## AirBnB clone - The console

## Introduction

Team project to build a clone of [AirBnB](https://www.airbnb.com/).

The console is a command interpreter to manage objects abstraction between objects and how they are stored.

The console will perform the following tasks:

- create a new object
- retrive an object from a file
- do operations on objects
- destroy an object

### Storage

All the classes are handled by the `Storage` engine in the `FileStorage` Class.

## Installation

```bash
git clone https://github.com/VictorMwachi/AirBnB_clone.git
```

change to the `AirBnb` directory and run the command:

```bash
 ./console.py
```

### Execution

In interactive mode

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```

in Non-interactive mode

```bash
$ echo "help" | ./console.py
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
```

## Usage

- Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

- Use help to see the available commands:

```bash
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb)
```

- Quit the console:

```bash
(hbnb) quit
$
```

### Commands

> The commands are displayed in the following format _Command / usage / example with output_

- Create

> _Creates a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json._

```bash
create <class>

```

```bash
(hbnb) create BaseModel
6cfb47c4-a434-4da7-ac03-2122624c3762
(hbnb)
```

- Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel 6cfb47c4-a434-4da7-ac03-2122624c3762
[BaseModel] (a) [BaseModel] (6cfb47c4-a434-4da7-ac03-2122624c3762) {'id': '6cfb47c4-a434-4da7-ac03-2122624c3762', 'created_at': datetime.datetime(2021, 11, 14, 3, 28, 45, 571360), 'updated_at': datetime.datetime(2021, 11, 14, 3, 28, 45, 571389)}
(hbnb)
```

- Destroy

> _Deletes an instance of a given class with a given ID._ > _Update the file.json_

```bash
(hbnb) create User
36a31df4-51b0-4523-8dfa-b3c7669cf47d
(hbnb) destroy User ff72a9a4-045a-48e2-9e97-8927c32dbd24
(hbnb) show User 36a31df4-51b0-4523-8dfa-b3c7669cf47d
(36a31df4-51b0-4523-8dfa-b3c7669cf47d) {'id': '36a31df4-51b0-4523-8dfa-b3c7669cf47d', 'created_at': datetime.datetime(2022, 9, 6, 18, 8, 11, 83847), 'updated_at': datetime.datetime(2022, 9, 6, 18, 8, 11, 83881)}
(hbnb)
```

- all

> _Prints all string representation of all instances of a given class._ > _If no class is passed, all classes are printed._

```bash
(hbnb) create BaseModel
1dd79ac4-b59b-4806-875e-152e0513850d
(hbnb) all BaseModel
["[BaseModel] (1dd79ac4-b59b-4806-875e-152e0513850d) {'id': '1dd79ac4-b59b-4806-875e-152e0513850d', 'created_at': datetime.datetime(2022, 9, 6, 18, 9, 51, 262207), 'updated_at': datetime.datetime(2022, 9, 6, 18, 9, 51, 262241)}"]
```

- count

> _Prints the number of instances of a given class._

```bash
(hbnb) count User
2
(hbnb)
```

- update

> _Updates an instance based on the class name, id, and kwargs passed._ > _Update the file.json_

```bash
(hbnb) update User 36a31df4-51b0-4523-8dfa-b3c7669cf47d email "ev@gmail.com"
(hbnb) show User 36a31df4-51b0-4523-8dfa-b3c7669cf47d
[User] (36a31df4-51b0-4523-8dfa-b3c7669cf47d) {'id': '36a31df4-51b0-4523-8dfa-b3c7669cf47d', 'created_at': datetime.datetime(2022, 9, 6, 18, 8, 11, 83847), 'updated_at': datetime.datetime(2022, 9, 6, 18, 8, 11, 83881), 'email': 'ev@gmail.com'}
(hbnb)

```
