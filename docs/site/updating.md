# Updating the site

The VNOJ is under active development, so occasionally you may wish to update. This is a fairly simple process.

!>  The VNOJ development team makes no commitment to backwards compatibility. It's possible that an update migration
    might add, change, or delete data from your install. Always back up before attempting an update. <br> <br>
    If in doubt, feel free to [contact us on Discord](https://discord.gg/TDyYVyd).

First, switch to the site virtual environment, and pull the latest changes.

```
(copevenv) $ git pull origin master
```

Dependencies may have changed since the last time you updated, so install any missing ones now.

```
(copevenv) $ pip3 install -r requirements.txt
```

The database schema might also have changed, so update it.

```
(copevenv) $ ./manage.py migrate
(copevenv) $ ./manage.py check
```

Finally, update any static files that may have changed.

```
(copevenv) $ ./make_style.sh
(copevenv) $ ./manage.py collectstatic
(copevenv) $ ./manage.py compilemessages
(copevenv) $ ./manage.py compilejsi18n
```

That's it! You may wish to condense the above steps into a script you can run at a later time.
