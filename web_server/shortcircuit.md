Gaia Tutorials
==============

First Day
---------

1. Set up accounts (Gaia web, email, ssh)
2. git clone the git_web repo
3. set up `temp/config.php`
4. `dev/test_db/__init__.php` to initialize all SQL tables
5. View sandbox in browser -- you should see a copy of the production site if successful

Hello World (First Week)
------------------------

1. ShortCircuit Wiki
2. Create a skeleton app `myfirstweek`.
    Echo "Hello World." from your ShortCircuit `index.template.php`
3. Change "Hello World." to "Hello {$myname}."
4. Secure this by validating the string and escaping it before _output_.
    Test XSS strings and verify that XSS is filtered.
5. Memcache persistence storage
    Store a virtual currency value in memcache.  Set it to 1.  Display the current currency value at the top of every page.
6. Currency actions
    Create a form with 3 actions to increase/decrease your virtual currency: vote (+10), post (+20), and tip (-5).
    Update the memcache value when an action is submitted.
7. Create a class: `\GaiaOnline\MyFirstInventory`
    
8. 
