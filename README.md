# Nozzlr v1.1 

Nozzlr is a multithread bruteforcer, trully modular and script-friendly - **author**: intrd@dann.com.br & github collaborators

The other bruteforce tools are amazing, but the hardcoded parameters make it painful to script 
over complex tasks. Nozzlr comes to solve this problem. All your task parameters/engine is 
managed directly in the task module(a python script). 

```
usage: nozzlr taskmodule wordlists threads [--offset] [--resume_each] [--quiet] [--help]

positional arguments:
  taskmodule            Task module filepath
  wordlists              Wordlist paths(space separated, 2 max)
  threads               The number of threads

optional arguments:
  -h, --help            show this help message and exit
  --offset [OFFSET]     >= 0 start from wordlist linenumber
  --resume_each [RESUME_EACH]
                        100 = default, save session every 1k tries
  --quiet [QUIET]       Supress most of program output (saves CPU)
  --repeats [REPEATS]   Loops the same wordlists N times, default=1

Just copy one of this samples below to your working directory and customize to your needs.  

default task modules:
  samples/argv_bruteforce.py : ARGV - pipe to commandline args (PoC: bruteforcing ccrypt)
  samples/stdin_bruteforce.py : STDIN - pipe inside commandline tools (PoC: bruteforcing LUKS)
  samples/ftp_bruteforce.py : RAW FTP (PoC: proFTPd, but works w/ any other server)
  samples/http_bruteforce.py : HTTP POST (PoC: bruteforcing pastd.com private notes)
  samples/ssh_bruteforce.py : SSH login (PoC: openSSH bruteforce)
  samples/argv_charbruteforce.py : ARGV - pipe to commandline args (PoC: char by char looping wordlist N times)

This is a proof-of-concept tool, any actions and or activities is solely your responsibility. 
The misuse of this tool can result in criminal charges brought against the persons in question. 
The authors and collaborators will not be held responsible in the event any criminal charges 
be brought against any individuals misusing this tool to break the law.

```
![nozzlr](/nozzlr.gif?raw=true "nozzlr bruteforcer")

Yes! your task modules/contributions are welcome :) 

##INSTALL
```
cd ~/ && git clone http://github.com/intrd/nozzlr appz/nozzlr && cd appz/nozzlr \
&& wget -O libs/int_netcat.py https://gist.github.com/intrd/00a39c83f752acf81775bfa9721e745a/raw/ \
&& sudo ln -s $PWD/nozzlr.py /usr/bin/nozzlr
```

##USAGE
```
Copy selected task xxx_bruteforce.py from /samples to your working directory, edit, and run:

nozzlr samples/ssh_bruteforce.py wordlists/unix_users.txt wordlists/unix_passwords.txt 1
```

##UPDATE
```
cd ~/appz/nozzlr && git pull \
&& wget -O libs/int_netcat.py https://gist.github.com/intrd/00a39c83f752acf81775bfa9721e745a/raw/
```

##CHANGELIST
```
v1.1
  - now processing multiple wordlists
```