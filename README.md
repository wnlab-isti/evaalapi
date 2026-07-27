# IPIN competition interface

For official use at the [IPIN competition](https://competition.ipin-conference.org/) you need a trial name.
    
For unofficial testing you can freely use the `demo` trial, either by
writing your own tests or by running the [demo](demo)
program at your premises.  Calling `demo auto` produces [this output](demo-auto.out)
on your terminal.  Calling `demo interactive` allows one to choose the timing by
pressing Return at the terminal.
    
If you want to run `demo` with an API server at your premises, you need to download
the API server source code and the [demo configuration](evaalapi.yaml) in the
same directory, plus the `Logfiles/01-Training/01a-Regular/T03_02.txt` file taken from
[Indoorloc](https://indoorloc.uji.es/ipin2020track3/files/logfiles2020.zip), to be put
under a `trials/` subdirectory.

## Documentation

You should start by carefully reading the [API complete documentation](https://evaal.aaloa.org/evaalapi/evaalapi.html)
(Markdown [source](evaalapi.md)) which begins with an overall decription of the API.
Once you are familiar with it, you can use the [OpenAPI description](https://evaal.aaloa.org/evaalapi/apidocs/) as a
reference with examples.

## Source code

Copyright 2021-2024 Francesco Potortì
    
The Python [evaalapi.py](evaalapi.py) source code is released under the
[GNU Affero General Public License v3.0 or later](https://www.gnu.org/licenses/agpl-3.0.html). 
