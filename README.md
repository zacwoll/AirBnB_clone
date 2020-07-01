# AirBnB clone - The console

<p align="center">
    <img src="https://i.imgur.com/JOhaZ5m.png">
</p>

## Description

This team project is part of the [Holberton School](https://www.holbertonschool.com/) Full-Stack Software Engineer program.
It's the first step towards building our first full web application: an AirBnB clone.
This first step consists of a custom command-line interface for data management and the base classes for the storage of this data.

## Usage

Our console works in interactive mode and non-interactive mode, like a Unix shell.
It prints the prompt **(hbnb)** and waits for the user for input.

Command | Example
------- | -------
Run the console | ```./console.py```
Quit the console | ```(hbnb) quit```
Display the help for a command | ```(hbnb) help <command>```
Create an object (prints its id)| ```(hbnb) create <class>```
Show an object | ```(hbnb) show <class> <id>``` or ```(hbnb) <class>.show(<id>)```
Destroy an object | ```(hbnb) destroy <class> <id>``` or ```(hbnb) <class>.destroy(<id>)```
Show all objects, or all instances of a class | ```(hbnb) all``` or ```(hbnb) all <class>```
Update an attribute of an object | ```(hbnb) update <class> <id> <attribute name> "<attribute value>"``` or ```(hbnb) <class>.update(<id>, <attribute name>, "<attribute value>")```
Count the number of instances of an object | ```(hbnb) <class>.count()```
Update attributes of an object using an dictionary | ```(hbnb) <class>.update(<id>, {dictionary representation})```

** Note **
For updating using a dictionary representation:
* If the attribute value is a string, use the format: `'key': "value"`
* If the attribute value is a number, use the format: `"key": value`

Non-interactive mode example

```bash
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update
```

## Models

The folder [models](./models/) contains all the classes used in this project.

File | Description | Attributes
---- | ----------- | ----------
[base_model.py](./models/base_model.py) | BaseModel class for all the other classes | id, created_at, updated_at
[user.py](./models/user.py) | User class for future user information | email, password, first_name, last_name
[amenity.py](./models/amenity.py) | Amenity class for future amenity information | name
[city.py](./models/city.py) | City class for future location information | state_id, name
[state.py](./models/state.py) | State class for future location information | name
[place.py](./models/place.py) | Place class for future accommodation information | city_id, user_id, name, description, number_rooms, number_bathrooms, max_guest, price_by_night, latitude, longitude, amenity_ids
[review.py](./models/review.py) | Review class for future user/host review information | place_id, user_id, text

## File storage

The folder [engine](./models/engine/) manages the serialization and de-serialization of all the data, following a JSON format.

A FileStorage class is defined in [file_storage.py](./models/engine/file_storage.py) with methods like so:
```<object> -> to_dict() -> <dictionary> -> JSON dump -> <json string> -> FILE -> <json string> -> JSON load -> <dictionary> -> <object>```

The [__init__.py](./models/__init__.py) file contains the instantiation of the FileStorage class called **storage**, followed by a call to the method reload() on that instance. This allows the storage to be reloaded automatically at initialization, which recovers the serialized data.

## Tests

All the code is tested with the **unittest** module.</br>
The tests for the classes are in the [test_models](./tests/test_models/) folder.</br>
Tests for File Storage are in [test_engine](./tests/test_models/test_engine).</br>
Tests for the console itself are in [tests](./tests/).</br>

## Shoutouts

This project was made possible through an alliance between Vim and Emacs users. </br>
This README was created in [stackedit.io](stackedit.io).</br>
This pandemic is the worst.</br>

## Authors

* **Tabitha O'Melay** - [github](https://github.com/tabbykatz) - [linkedin](https://www.linkedin.com/in/tabbykatz/) - [twitter](https://twitter.com/tabby__katz)
* **Cynthia Taylor** - [github](https://github.com/cg-taylor) - [linkedin](https://www.linkedin.com/in/cynthia-taylor/) - [twitter](https://twitter.com/wholockwars)
* **Zac Woll** - [github](https://github.com/zacwoll) - [linkedin](https://www.linkedin.com/in/zachary-woll-52021a1a1/) - [twitter](https://twitter.com/ZakWoll)
