# Simple steps to connecting to PostgreSQL server on Elementary OS terminal

After successfully installing postgresql on your local machine, the next this to connect to it and begin querying the database but however on other OS such as windows, the installation comes with something called psql shell and PgAdmin.


This however is not available on elementary os but theres no cause for alarm we can connect using the default terminal that come preinstalled with the OS. You can follow this steps to connecting on debian/ubuntu platforms and other linux environments.

In this tutorial I'll be showing how to connect to PostgreSQL database server from terminal using following simple steps.

Without wasting much of our time, let's dive into it.


-  Fire up the terminal by pressing `Command + space` and search the applications by typing terminal in the searchbox or press `Command + T`. For other ubuntu variance you can just press `Ctrl + Alt + T`.

Once the terminal is up, 


-  Next on the terminal type `sudo -i -u postgres` to authenticate, the command will ask for user password, by default the postgres user created will be linked to the admin or root user using ident, This means that PostgreSQL will associate its roles with the system accounts of Linux. You can check [here...](https://www.postgresqltutorial.com/install-postgresql-linux/) for more info.

The postgres user is created when you installed PostgreSQL, the installation process created a user account called postgres associated with the default postgres role.


After keying in the password


- Then type psql

psql is an interactive terminal program provided by PostgreSQL. It allows you to interact with the PostgreSQL database server such as executing SQL statements and managing database objects.

You should get the same output based on your system configuration similar to the screenshot below.

<image 2>

And there you have it, I hope you find the simple steps very helpful.

Next I'll be writing on how to connect to the postgresql using the PgAdmin graphical user interface.

If you like my contents you can connect with me on [LinkedIn](https://www.linkedin.com/in/ola-ishola/) and on [Twitter](https://twitter.com/Orlaish)







