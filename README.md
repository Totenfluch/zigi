# zigi (v1.0 alpha)
zdevops ISPF git interface

Interfacing with git on The Mainframe straight out of ISPF.
Initial blogpost : http://zdevops.tumblr.com/post/171450515585/git-straight-outta-ispf 

https://streamable.com/qa2th

## Installation Instructions
* copy ZDO.PROD.ISPCLIB(ZGADD) to one of your "ISPCLIB"-datasets
* copy ZDO.PROD.ISPPLIB(ZDOGIT00) to any library (it's dyn-alloced)
* change 'GITDIR' and 'PANEL' variables in customization section of ZGADD

## Usage
Just type 'zgadd' in front of any member or library(pds).

## Prereqs
You need to have GIT installed on your box :)
To do so you need to download the latest version of bash, gzip, perl and git from rocketsoftware.
Then place them in a directory within your USS environment and add the installer script from this gist (https://gist.github.com/wizardofzos/897b243d4cbe9fbc471ec1396fbbe174)

## TODO:
* add 'pushing' capabilities (sort of implemented)
* add 'pulling' capabilities (zgpull)
* add features to work with branches

## Current (1.1) pushing
Make sure to *manually* do a git remote add origin <your repo uri> and a 
git push -u origin master.                         
Also do a (local) git config user.name and user.mail.
Then, when you ZGADD a member (or PDS/Library) it will be auto pushed
--> THERE IS NO PULL YET. This probably means if remote is updated, the push
will break :)
