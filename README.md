# Samba-Server
File Sharing Server 

1.Install Samba Server
 
      sudo apt-get install samba
      
2.Take a backup original samba.conf

      sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.back
      
3.Config Samba conf File

      sudo nano /etc/samba/smb.conf
      
      workgroup = test.local (your name)
      
      #save and exit
      
4.create two directory name as (example)

      *. private - mkdir private
      *. public  - mkdir public
      
5.Change the permission of the public directory for public access and change private as private access
      
      sudo chmod 777 public
      sudo chmod 777 privte (but can't access others)

      
6.Add a detalis in to the samba config file

    sudo nano /etc/samba/smb.conf
    
    [My Public share]
    path = /home/test/public
    guest ok = yes
    writable = yes
    
--------------------------------------------------------------   
7. # File Or Directory Access For Special User

1.Create New User Account and add new user in samba database
  
  sudo adduser sam
  sudo smbpasswd -a sam
  
2.Config the private Directory for New User "Sam"

    sudo nano /etc/samba/smb.conf
    
    
    [Sam Private Share]
    path = /home/test/priavte
    valid users = sam
    writable = yes
