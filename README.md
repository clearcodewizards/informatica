# HAVO informatica
HAVO informatica: Leren omgaan met HTML

## Vereisten
- Python3 te downloaden via https://www.python.org/downloads/
- Sublime Text editor via https://www.sublimetext.com/

## Ontwikkelomgeving
Voor deze opdracht heb je flask nodig dit is een webserver die je lokaal kunt draaien.

### Installeer python virtual environment
Open het programma terminal en voer de volgende commando's uit:
```
$ mkdir html
$ cd html
$ python3 -m venv .venv
```

Voordat je onderstaande taken kunt uitvoeren moet je de python virtuele omgeving geladen hebben via:
```
$ . .venv/bin/activate
```

### Installeer flask
```
$ pip install flask
```

### Je eerste website
Maak een file app.py aan in de huidige folder (html) met de volgende inhoud:
```
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<html><head><title>Website</title></head><body><p>Hallo, wereld!</p></body></html>"
```

Start nu flask en je kunt met je browser je website zien: http://127.0.0.1:8080
```
$ flask run -p 8080
```

### HTML templates
Met flask kun je ook heel makkelijk gebruik maken van HTML templates zodat je straks ook gebruiker data kunt verwerken.

Pas app.py aan naar het volgende:
```
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def hello_world():
    return render_template('hello.html')
```

Zoals je kunt zien maken we nu gebruik van een html bestand hello.html.

Deze moet je wel zelf eerst aanmaken voordat dit gaat werken. Flask zoekt naar hello.html in een folder templates dus deze folder moet je ook eerst aanmaken en daarna het bestand hello.html in deze folder plaatsen.
```
$ mkdir templates
$ subl templates/hello.html
$ flask run -p 8080
```
