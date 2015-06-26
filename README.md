Make sure VirtualBox and Vagrant are installed before proceeding.

### From Windows Git Bash prompt
    vagrant plugin install vagrant-vbguest
    vagrant plugin install vagrant-librarian-chef-nochef
    vagrant plugin install vagrant-multi-putty
    
### Change directory to your Rails project folder from in Git Bash
    cd projects
    cd my_rails_project

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
