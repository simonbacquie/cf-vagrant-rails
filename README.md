# Setup

Make sure VirtualBox and Vagrant are installed before proceeding.

### From Windows Git Bash prompt
    vagrant plugin install vagrant-vbguest
    vagrant plugin install vagrant-librarian-chef-nochef
    vagrant plugin install vagrant-multi-putty
    
### Change directory to your Rails project folder from in Git Bash
This goes for wherever your project folder is:

    cd my_rails_project
    
### Copy files from this repo into your Rails project folder
    Vagrantfile
    Cheffile
These contain a pre-made configuration for the Virtual Machine we're about to build.

### Add to .gitignore in Rails project
    .vagrant
    cookbooks/
This step is very important. Without this, you'll likely end up with a huge (5 GB or so) Virtual Machine file checked into your Git repo, which GitHub will reject for being too large on your next push.
    
### From Git Bash in Rails project folder
    vagrant up
Wait while Ubuntu, Ruby, etc. are installed... you'll see a lot of text.
    vagrant ssh
This connects to the VM and gives you a command prompt in the Linux environment. The prompt should look something like:
    vagrant@vagrant-ubuntu-trusty-64

### Once inside the VM
    git config core.filemode false
    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com
    gem install bundler
    
### Go to your project folder from within the VM
    cd /vagrant
    ls
The `ls` command should show list your Rails project's files.
    
### Start Rails server inside VM
    bundle exec rails server
    
Inside a browser in Windows, go to http://localhost:3000, and you should see a webpage served up from your Rails app!

# Working with Vagrant VMs

Virtual Machines are like a another computer running inside your computer. As such, you have to start it up and shut it down like an actual computer. You can start it up by using cd to get into your project folder (from a Windows prompt) and running:

    vagrant up
Once the VM is running, you can connect to it and get a command line with:

    vagrant ssh
You can shut down the machine with:

    vagrant halt

You'll want to shut down the VM when not working on development stuff, as it consumes a lot of memory and will slow down your machine/use up battery life.
