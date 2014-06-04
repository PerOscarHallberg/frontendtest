#How to install Frontend Test

## Installing on your Mac machine
 - make sure you have apache server [enabled on your Mac](https://gist.github.com/krisrybak/548fc5885254216a1a9b)
 
 - make sure you have git [enabled on your Mac](https://gist.github.com/krisrybak/78cc675caed9715bfb1f)
 
 - go to /home/sites and clone the source

        cd /home/sites && git clone git@github.com:{YOUR_GITHUB_USERNAME}/frontendtest.git

 - install the vhost

        cd frontendtest && cp config/frontendtest.conf /home/vhosts/

 - add bradley dyer as remote

        git remote add bd git@github.com:bradleydyer/frontendtest.git

 - add post-merge hook to your git config

        sudo vi .git/hooks/post-merge

   Add following line (press A to enter Insert mode):

        git branch --merged master | grep -v 'master$' | xargs git branch -d

   Save you changes: `ESC, :wq`

   Change permissions on the file you have just created:

        sudo chmod 0755 .git/hooks/post-merge

 - add entry to your hosts file

        sudo vi /private/etc/hosts

 - and add

        127.0.0.1       frontendtest.local

 - reset your apache

        sudo apachectl restart
