# Buildout base Plone 6


sudo pip3 install virtualenv


### Establish owners for existent user and group 
#### (plone_buildout:plone_group)
chown -R plone_buildout:plone_group  ./


### Create egg-cache on some directory and establish owners
#### In this case we use this path : /opt

cd /opt

mkdir -p .buildout/{downloads,eggs,extends,zope}

cd .buildout

chown -R plone_buildout:plone_group  ./


### Inside project

cd /opt/plone609

### Create virtual environtment with desired python executable
virtualenv -p /usr/local/bin/python3.11 .


### Activate de environtment
source bin/activate

### Install requirements
pip install -r requirements.txt


### Buildout
buildout -Nv