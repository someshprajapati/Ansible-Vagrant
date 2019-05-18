# Ansible-Vagrant

Get this app up and running on a Vagrant VM using your known production best practices as well as the instructions in the guidelines below.

You should use provisioner to install and configure everything. Ansible is preffered. But you can use chef or puppet if you more familiar with those tools. (please don't use shell provisioner).

When you're done, we should be able to type vagrant up and our app will be running and reachable on http port 80 at http://10.10.10.20
Guidelines:

   1) The provisioner should clone this github repo into the VM under /webapps/devops
   2) You should be able to find what system packages are needed by looking through the app
   3) You should not need to change the app code in any way
   4) The app should be running as a non-privileged user
   5) The app should be automatically restarted if crashes or if killed
   6) The app should maximize all of the available CPUs (have
   7) Vagrant virtualize multiple CPUs)
   8) The related logs should be rotated
   9) Timezone should be in UTC


