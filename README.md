# User & Group Add | Delete | Modify in Linux System

<p>
    User management is a very important task. In Linux system there are different types of user exit. Basically there are 3 types of user in Linux system. 
</p>

1. root: 0
2. system user: 1-999
3. regular user: 1000+

> Note: Here, 0 represents the root user's UID and 1-999 represents the system user's UID.

## Check UID

<p>
    We can check any individual user's UID by the help of id command.
</p>

```
id root
id mail
id kmsaifullah
```

## Task-1

<p>
    Create a new user with the username john and show the user using the bash terminal.
</p>
 Solution:

```
useradd john
id john
grep john /etc/passwd
```

> All user information will contain or store in the /etc/passwd file file in Linux System. We can confirm that any user exist or not in a system by reading the /etc/passwd file. On the other hand all the passwords of user will store in the /etc/shadow file.

<p>
    After successfully creating an user we can see the user information from the following command:
</p>

`grep john /etc/passwd`

Output of the command will look like

```
john:x:1006:1007::/home/john:/bin/bash
```

Now, let's talk about this output. First we need to break this output some parts.

1. john : It indicates the username of this user.
2. x : This represents the password information and this information will exist in /etc/shadow file
3. 1006 : This is the UID of john
4. 1007 : This is the primary group id(GID) of this user.
5. : : This field is empty. It will define the fullname and other information of the user.
6. /home/john : This is the home directory of the user.
7. /bin/bash : This is the user's default shell.

## Task-2

<p>
    Set a new password as 12345 to the new user john.
</p>

Solution:

```
passwd john
```

> then type the password [12345] and confirm the password.

## Task-3

<p>In this task you need to do multiple things. First create four new user as jane,jake,jonas and jave. Then create two new groups. The new groups name will be admin and sales. Assign jane and jave to the admin group and assign rest of them in sales group.</p>

Solution

```
useradd jane
useradd jake
useradd jonas
useradd jave

groupadd admin
groupadd sales

usermod -G admin jane
usermod -G admin jave
usermod -G sales jake
usermod -G sales jonas
```
