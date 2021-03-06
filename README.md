Hunch Gift Application
================================

This application will display gift recommendations for any Twitter
user and is an example of what can be built using the [Hunch
API](http://hunch.com/developers/). The code is almost identical to
that powering the [Hunch Gift-o-Matic](http://hunch.com/apps/gifts/). The
application is built to run either as a standalone
[Django](http://www.djangoproject.com/) application or using [Google
App Engine](http://code.google.com/appengine/).

Other libraries used include:

* [jQuery JavaScript Framework](http://jquery.com/)
* [Mustache JavaScript templating library](http://github.com/janl/mustache.js)
* [Hunch JavaScript SDK](http://hunch.com/developers/v1/resources/samples/)
* [djangoappengine](http://www.allbuttonspressed.com/projects/djangoappengine)


Getting started
---------------

1. Download the [Google App Engine Python SDK](http://code.google.com/appengine/downloads.html)

2. Test your app loads the test page
   * run `python dev_server.sh` (this defaults to running on port 80 which may require root permissions)
   * open a web browser and navigate to [http://localhost](http://localhost)
   * ensure that you see the success page
   * now navigate to [http://localhost/gifts/](http://localhost/gifts/)
   * ensure that you can enter a twitter name and get recommendations

3. When ready, deploy the app to GAE
   * in settings.py, create a SECRET_KEY
   * `python manage.py deploy`


Useful commands
---------------

Start the development server
`sh dev_server.sh`

Publish your app to GAE
`python2.5 manage.py deploy`

Launch a local Python console for interecting with the app and datastore
`python2.5 manage.py shell`

Launch a remote Python console for interacting with the app and datastore
`python2.5 manage.py remote shell`


Notes and gotchas
-----------------

* GAE will penalize your app if requests take over 1000 ms to complete, so
push as many calls to the frontend as possible by using the
[Hunch Javascript SDK](http://hunch.com/media/js/hunch-api.js)

* This application is packaged with [djangoappengine](http://www.allbuttonspressed.com/projects/djangoappengine)
for creating Django projects that run on GAE. It is worthwhile to read the [overview of using the helper](http://code.google.com/appengine/articles/django-nonrel.html).

* GAE uses Python 2.5, so running scripts like `manage.py` with python2.5 is
recommended. The scripts `dev_server.sh` and `fresh_dev_server.sh` use python2.5

* You can access the GAE admin console at [http://localhost/_ah/admin/](http://localhost/_ah/admin/)

* For testing, it is useful to redirect your-app-name.appspot.com to your local machine.
To accomplish this, edit your /etc/hosts file and point that address to your IP (or localhost)
