I followed the Flask tutorial on flask.pocoo.org
flask Version: 0.10

I ran into some problems at step 2 and step 3 which I was able to fix.

Here's what I did:
- install SQLite3
- under \flaskr directory, make another directory \tmp, in \tmp create an empty file "flaskr.db"
- since I use Windows here, in flaskr.py I change the path of DATABASE into:
     
	DATABASE = 'C:\\Users\\Yao\\projects\\flask_projects\\flaskr\\tmp\\flaskr.db'

- also, in this part:
	
	app = Flask(__name__)
	app.config.from_object(__name__)
	app.config.from_envvar('FLASKR_SETTINGS', silent=True)
  
  I put app.config.from_object(__name__) back. For some reason, I thought I need to replace
it with app.config.from_envvar('FLASKR_SETTINGS', silent=True). But without it, there's error.

