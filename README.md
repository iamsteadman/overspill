# Overspill.io

List overflow talks for conferences

## Getting started

### To run the site locally:

1. If you haven't already, install [Vagrant and Ansible](https://adamcod.es/2014/09/23/vagrant-ansible-quickstart-tutorial.html) on your system
2. Clone the repo to a directory on your desktop
3. From that directory, run `vagrant up`
4. To run the development server, type `./devserver`
5. Visit http://192.168.60.110:8000/ in your browser

#### Running management commands

You can run management commands on behalf of the web console by simply typing
`./run <command> <args>`. The command name and args are piped through Vagrant's
SSH utility to the project's manage.py file, via a shortcut script that is
pre-loaded with all the necessary environment variables and the settings file.

This makes it ideal for things like generating schema migrations:

```
./run makemigrations
```

Thing is, I suck at Unix, so you can't put more than one argument after `~/run`
at the moment.

#### Running tests

The development servers are spun up with testing in-place, and there's a
shortcut function for testing the apps within Overspill. From the project
directory, just run `./test <app-name>` and the tests should run; you should
also get a coverage.py report back.

### To run the site remotely:

1. Create 3 DigitalOcean droplets: one for web, one for the database, and one for the worker
2. Copy `provisioning/digitalocean.sample` to `provisioning/digitalocean`
3. Replace the IP addresses with the ones you setup in step 1

More instructions coming
