from ast import Continue

import re
from getpass import getpass
def register():
  email=input("enter email: ")
  password=getpass("enter the password: ")
  b=re.match('[a-z][a-z0-9]+@[a-z]+\.[a-z]+$',email)
  c=re.findall('^.(?=.{5,16})(?=.\d)(?=.[a-z])(?=.[A-Z])(?=.[!@#$%^&?]).*$',password)
  f1=open("file has to save" ,"w")  
  if b:
    f1.write(f'Username:{email}' "\n")
    print("ok your mail is verified creat the pass word")
  else:
    print("your mail is missmatch is m")
  if c:
    f1.write(f'Password: {password}' "\n")
    f1.close()
    print("your password is rite")
  else:
    print("not valid")
def login():
  while True:
    email=input("enter email: ")
    password=getpass("enter the password")
    f1=open("file has to save","r").read()
    if email and password in f1:
      print("welcome")
      break
    else:
      print("Invalid user name or password")
      Continue
      f1.close()

print("Enter reg to register")
print("Enter log to login")
reg_or_login =input('do you want to register or login')
if reg_or_login=="reg":
  register()
elif reg_or_login=="login":
  login()
