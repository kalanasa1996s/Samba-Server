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
      
5.Change the permission of the public directory for public access
      
      sudo chmod 777 public
      
6.Add a detalis in to the samba config file

    suod nano /etc/samba/smb.conf
    
    [My Public share]
    path = /home/test/public
    guest ok = yes
    writable = yes
    
    
      
