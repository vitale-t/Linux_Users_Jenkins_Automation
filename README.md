# Linux_Users_Jenkins_Automation

A declarative pipeline in Jenkins that allows you to create users on a Linux system, generating a temporary password that the operator can send to the end user. The steps to configure and run the job are detailed below.

Access to Jenkins: You must have access to a Jenkins instance with permissions to create and run pipelines.
Sudo Permissions: The user under which Jenkins runs must have sudo permissions to execute the following commands without requiring a password: groupadd, useradd, chpasswd, passwd.
Sudo Configuration:To prevent Jenkins from prompting for a password when running sudo commands, edit the /etc/sudoers file and add the following line (replace jenkins_user with the user under which Jenkins runs).
"jenkins_user ALL=(ALL) NOPASSWD: /usr/sbin/groupadd, /usr/sbin/useradd, /usr/bin/chpasswd, /usr/bin/passwd"
This allows the Jenkins user to execute the necessary commands without a password.
The user under which Jenkins runs is usually jenkins or the user you configured during installation.

Usage Instructions:
Create a Pipeline in Jenkins:In Jenkins, go to New Item. Select Pipeline and give the job a name (e.g., Create Linux User). In the Pipeline section, select Pipeline script and paste the contents of the Jenkinsfile.
Run the Job: Once the job is created, click Build Now. The pipeline will prompt for the following data:
Operator Login: Enter the login of the operator running the job (e.g., ana.gomez).
First Name: Enter the first name of the user to be created (e.g., Juan).
Last Name: Enter the last name of the user to be created (e.g., Pérez).
Department: Select the department to which the user belongs (Accounting, Finance, or Technology).
Execution Result: If the job runs successfully, the information will be displayed in the Jenkins console. The generated temporary password should be copied and sent to the end user for their first login.
