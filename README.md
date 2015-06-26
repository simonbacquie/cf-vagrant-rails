### From Windows Git Bash prompt
    vagrant plugin install vagrant-vbguest
    vagrant plugin install vagrant-librarian-chef-nochef
    vagrant plugin install vagrant-multi-putty


### Add to .gitignore in Rails project
    .vagrant
    cookbooks/
    
### From Git Bash in Rails project folder
    vagrant up
( wait a long time while Ubuntu, Ruby, etc. are installed )
    vagrant ssh
( this connects to the VM and gives you a command prompt in the Linux environment )

### Once inside the VM
    git config core.filemode false
    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com
    gem install bundler
    
### Go to your project folder from within the VM
    cd /vagrant
    ls
( the ls command should show list your Rails project's files )
    
### Start Rails server inside VM
    bundle exec rails server
    
Inside a browser in Windows, go to http://localhost:3000, and you should see your Rails app!
