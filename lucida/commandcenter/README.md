# Command Center (CMD)

The command center has the following functionalities:

- Sets up the web front end.
- Maintains a list of registered back-end services.
- Classifies and forwards front-end requests to the appropriate services.
- Returns requested information to the front end.

Specifically, `app.py` starts the Flask server (listening to front end),
the Thrift server (listening to back end),
and web socket ASR router (listening to front end).

## Major Dependencies

- [Flask](http://flask.pocoo.org/)
- [Apache Thrift](https://thrift.apache.org/)
- [Tornado](http://www.tornadoweb.org/en/stable/)
- [scikit-learn](http://scikit-learn.org/stable/)

## Structure

- `controllers/`: web controllers, database module, Thrift modules, utilities module, 
query classification module, configuration file (`Config.py`), etc.
- `data/`: training data for query classifier (to which you are welcome to contribute)
- `inputs/`: testing data
- `static/`: static contents of the web front end
- `templates/`: html Jinja templates
- `app.py`: top-level module
- `clear_db.sh`: script to clear MongoDB

## Build

```
make
```

This generates Thrift modules and thus only needs to be done once.
To change configurations such as whether to train or load models
for the query classifier, modify `controllers/Config.py` by reading
the instructions in the file.

## Run

Start the server:

```
make start_server
```

Open your browser and go to `http://localhost:3000/`. 