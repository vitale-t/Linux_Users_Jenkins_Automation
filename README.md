# Linux_Users_Jenkins_Automation

Jenkins pipeline that allows you to create users on Unix systems, generate a temporary password assigned to the user (which the end user must change upon initial login), and retrieve it for copying and emailing.

Note: Access to Jenkins. You must have access to a Jenkins instance with permissions to create and run pipelines. The user running the pipeline must have sudo permissions to run the following commands: groupadd, useradd, chpasswd, and passwd. Sudo Configuration: To prevent Jenkins from prompting for a password when running sudo commands, edit the /etc/sudoers file and add the following line: "JENKINS ALL=(ALL:ALL) NOPASSWD:/usr/bin/passwd -e *, /usr/sbin/useradd, /usr/sbin/usermod, /usr/sbin/chpasswd, /usr/bin/passwd --expire, /usr/sbin/groupadd, /usr/sbin/groupdel". This allows the Jenkins user to run the necessary commands without a password.
