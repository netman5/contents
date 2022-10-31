# Steps to connecting to PostgreSQL server on Elementary OS & other Linux terminal

Connecting to postgres server in the command line is something I have to google every time I'm working with PostgreSQL, I know you must be thinking is this guy retarded or what! I'll leave you to answer that. I guess we all forget things, at times we all struggled to remember basic things after so long time which is completely fine, their is this popular jokes in tech about googling how to center a div, their is no crime in googling things but when you have to google the same thing over and over again then why not just have it documented somewhere for a quick reference.

Read about people using their blog as a memory dump, this is me writing this for my future self for a point of reference, for others like me and for beginners. There are others ways of connecting to the postgres server apart from using the terminal such as the pgAdmin etc. Feel free to use whatever that works for you.

After successfully installing PostgreSQL on your local machine, the next thing is to connect to it and begin querying the database isn't it?  However on other OS such as windows, the installation comes with something called psql shell.

This however is not available on elementary OS by default but theirs no cause for alarm we can connect using the default terminal that come preinstalled with the OS. You can also follow this steps to connecting on Debian/Ubuntu platforms and other Linux environments.

In this article I'll be showing how to connect to [[PostgreSQL]] database server from terminal using following simple steps and my believe is that you have successfully installed PostgreSQL on your local machine since this article is not and won't be about installation.

Without wasting much time, let's dive into it.

-  Fire up the terminal by pressing `Command + space` and search the applications by typing terminal in the search box or press `Command + T`. For other Ubuntu variance you can just press `Ctrl + Alt + T`.

Once the terminal is up, 
-  Next on the terminal type `sudo -i -u postgres` to authenticate, the command will ask for user password, by default the postgres user created during installation will be linked to the admin or root user using ident, This means that PostgreSQL will associate its roles with the system accounts of Linux. You can check [here...](https://www.postgresqltutorial.com/install-postgresql-linux/) for more info.

The postgres user is created when you installed PostgreSQL, and the user is associated with the default postgres role.

After keying in the password should get something similar to the below screenshot.
![[postgres login.png]]

- Then type `psql`
psql is an interactive terminal program provided by PostgreSQL. It allows you to interact with the PostgreSQL database server such as executing SQL statements and managing database objects.

You should get the same output based on your system configuration similar to the screenshot below.
![[psql.png]]

From there you can type the name of the database you want to work on

Another way to connect using both psql and the database name as a single command
`psql databasename` 
![[psql dbname.png]]

From the above screenshot I used a TestDB as the selected database to connect to with the psql as a single command.

And there you have it, I hope you find the simple steps very helpful.

If you like my contents you can connect with me on [LinkedIn](https://www.linkedin.com/in/ola-ishola/) and on [Twitter](https://twitter.com/Orlaish)

Thanks for reading.






