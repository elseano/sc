# Server Connect

A simple bash script to make connecting to servers easier.

Stores a library of servers along with connection information for quick access to them via SSH without
having to stuff around with your hosts file.

## Basic Usage

Logs into the named server:

    sc [name]

Lists all the servers you can log into

    sc     

Shows the login and IP details for the given server

    sc -i [name]

Shows the hostname of the given server

    sc -h [name]

Copies your public key over to the server for passwordless entry (requires ssh-copy-id)

    sc -k [name]                 

Adds a server to the SC library

    sc -a [name] [ip] [user]

Adds a server to the SC library, and installs your public key

    sc -ak [name] [ip] [user]    

## Cool things

Use with `scp`:

    scp `sc -i yourserver`:/somedir/somefile.jpg .

Use with `ssh` tunnelling:

    ssh -L 3030:`sc -h target`:8000 `sc -i gateway`