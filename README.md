# IPIN competition interface

This GitHub repo includes the code for the FLASK server used in the [IPIN competition](https://competition.ipin-conference.org/).  

In order to participate in the competition you need to register on the competition website to one suitable track and later obtain a trial name from the track chairs.  

You can also install the server on your own premises and test the server API locally.

## Installation instructions

The following instructions describe how to setup and start a local server and heve been tested on a Linux Ubuntu 24.04 system with Python 3.12.3.

- Open a bash terminal  

- Clone the repository  

```bash
        $> git clone https://github.com/wnlab-isti/evaalapi.git
```

- Create a virtual environment  

```bash
        $> cd evaalapi
        $> python3 -m venv venv
```

- Activate the virtual environment  

```bash
        $> source venv/bin/activate
```

- Install project dependencies  

```bash
        $> pip install -r requirements.txt
```

- Run the FLASK server  

```bash
        $> FLASK_APP=evaalapi.py flask run --host=127.0.0.1 --port=54321
```

## Demo trial
    
For unofficial testing you can freely use the `demo` trial, either by writing your own tests or by running the python [demo](demo) program at your premises.  
Calling `demo auto` produces [this output](demo-auto.out) on your terminal.  
Calling `demo interactive` allows one to choose the timing by pressing Return at the terminal.
    
If you want to run `demo` with an API server at your own premises, you need to setup and start a local API server 
as described above.  
You also need to edit file [demo](demo) and change the server url line

```python
        server = "https://evaal.aaloa.org/evaalapi/"
```
with

```python
        server = "http://127.0.0.1:54321/evaalapi/"
```

File [evaalapi.yaml](evaalapi.yaml) contains the definition of the demo trial that will be used by the [demo](demo) python program.  
The demo trial sensor data is available in file [trials/T03_02.txt](trials/T03_02.txt) and will be read by the local API server to answer requests from the demo program.  

The [demo](demo) python program requires the following python extension packages: ```requests, parse, and PyYAML```.  
These are provided by the virtual environment created in the [Installation instructions](#Installation-instructions) section, so the simplest way to run the [demo](demo) program is to use it:

```bash
        $> cd evaalapi
        $> source venv/bin/activate
        $> chmod u+x demo
        $> ./demo auto
```

## Documentation

You should start by carefully reading the [API complete documentation](https://evaal.aaloa.org/evaalapi/evaalapi.html)
(Markdown [source](evaalapi.md)) which begins with an overall decription of the API.
Once you are familiar with it, you can use the [OpenAPI description](https://evaal.aaloa.org/evaalapi/apidocs/) as a
reference with examples.

## Source code license

Copyright 2021-2024 Francesco Potortì
    
The Python [evaalapi.py](evaalapi.py) source code is released under the
[GNU Affero General Public License v3.0 or later](https://www.gnu.org/licenses/agpl-3.0.html). 
