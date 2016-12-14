# jenkins

## Commands (OS X)
- `sudo launchctl load /Library/LaunchDaemons/org.jenkins-ci.plist`
- `sudo launchctl unload /Library/LaunchDaemons/org.jenkins-ci.plist`
- **Change Port**: `sudo defaults write /Library/Preferences/org.jenkins-ci httpPort 5757`

## Chnange Jenkins user
http://goodliffe.blogspot.com/2011/09/how-to-set-up-jenkins-ci-on-mac.html
- Edit */Library/LaunchDaemons/org.jenkins-ci.plist**, change the username entry from daemon to jenkins
- Change all permissions on the existing jenkins files: 
    - sudo chown -R [USER_NAME] /User/Shared/jenkins
    - sudo chgrp -R [GROP_NAME] /User/Shared/Jenkins"
    - sudo chown -R [USER_NAME] /var/log/jenkins
    [Optiona]
    - chown -R [USER_NAME] /var/lib/jenkins
    - chown -R [USER_NAME] /var/run/jenkins
    - chown -R [USER_NAME] /var/cache/jenkins
    
## ISSUES: 
###Launchd is not starting Jenkins server on OS X Yosemite
http://stackoverflow.com/questions/26483089/launchd-is-not-starting-jenkins-server-on-os-x-yosemite
- `sudo chmod 777 /var/log/jenkins`
- `sudo chmod 777 /Users/Shared/Jenkins/`
- `sudo chmod 777 /Users/Shared/Jenkins/tmp/`