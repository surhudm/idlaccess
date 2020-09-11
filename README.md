# IDL access from IUCAA

In order to access the IDL license from your own computer, follow these directions for your linux machine.

## Install IDL 8.7.3

Install IDL 8.7.3 from the IDL installer. You can get an idl installer from the algol.ac.iucaa.in.

```
scp algol.ac.iucaa.in:/opt/idl-8.7.3/idl-8.7.3/*.tar.gz .
tar -zxvf idl873-linux.tar.gz
sh install.sh
```

Give the correct install path. When it asks if you need to run the license administrator, please say no.

## Create a ssh tunnel to IUCAA license server.

```
ssh -N -L 7070:localhost:7070 algol.ac.iucaa.in
```

Give the password, this command will hang on the terminal. Keep this terminal open, and do not close it.

## Borrow license from server

Run the following command on another terminal.
```
harrislicense
```

* Select `Borrow licenses from a server`. 
* Enter `Server` as `localhost`, and `port` as `7070`.
* Choose borrow time and quantity of licenses.
* Click `Borrow from server`
* Once the license is successfully borrowed, close the license manager.
* You can also close the ssh tunnel by pressing Ctrl-C.

## Run idl

If all goes well, idl should be up and running.

```
idl
```

## For returning licenses

* Create the ssh tunnel to IUCAA license server again
* Run `harrislicense` for license management
* Open `Borrow licenses from a server`
* Click `Return all borrowed licenses`
