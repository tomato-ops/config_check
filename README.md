# config_check
compares and sends an email if the running config differs from a known state


install pip3 packages
```
sudo pip3 install -r requirements.txt
```

edit **compare** with your SSH key, your username, and IP address 
```
ssh -i /home/centos/key.pem user@0.0.0.0 show run > last
```

edit **email** with your email credentials and your recipient
```
sender_email = "@gmail.com"  # Enter your address
receiver_email = "@blah.com"  # Enter receiver address
password = "" # Enter email password
```

run **initial** to populate **show_run_base** with the initial running config
```
./initial
```

run **compare** to compare the current running config with your initial config, if there is a difference you should receive an email with the contents of **last**
```
./compare
```
