# Tips

When setting up a link to an executable, always use ABSOLUTE path to represent the executable file.  
WRONG one!! (Even if you are alreasy in ```$ /opt/Postman/``` directory)
```scipting
sudo ln -s ./Postman /usr/bin/postman
``` 

CORRECT ONE:
```scipting
sudo ln -s /opt/Postman/Postman /usr/bin/postman
```