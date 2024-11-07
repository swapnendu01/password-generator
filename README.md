# password-generator
generate a unique password

#importing the tiknter module
from tkinter import *

#importing the pyperclip module to use it to copy our generated password to clipbord
import pyperclip

import random
#initializing the tiknter
root= Tk()

#setting the width and height of the gui
root.geometry("400x400")

#declaring a variable of string type and this variable will be used to store the password genorated
passtr=StringVar()

#declaring a variable of integer type which will be used to stor the length of the password entered by the user
passlen=IntVar()

#setting the length of the password to zero initially
passlen.set(0)

#function to generate the password
def generate():
    pass1 = ['a','b','c','d','e','f','g','h','i','j','k',
            'l','m','n','o','p','q','r','s','t','u','v','w',
            'x','y','z','A','B','C','D','E','F','G','H','I', 
            'J','K','L','M','N','0','P','Q','R','S','T','U','V','W','X','Y','Z','1','2','3',
            '4','5','6','7','8','9','0','',',','#','$','%','^','&','*','(',')']

#declaring the empty string
    password=""

#loop to generate the random of the length entered by user
    for x in range(passlen.get()):
        password = password + random.choice(pass1)

# setting the password to the enter widget
    passtr.set(password)

#FUNCTION TO copy the password to the clipboard
def capytoclipboard():
    random_password= passtr.get()
    pyperclip.copy(random_password)

#creating a text label widget
Label(root, text="password generator application", font="calibri 20 bold").pack()

#creating a text label widget
Label(root, text="enter password length").pack()

Entry(root, textvariable=passlen).pack(pady=3)

Button(root, text="generate password", command=generate).pack(pady=7)

Entry(root, textvariable=passtr).pack(pady=3)

Button(root, text="copy to clipboard", command=generate).pack(pady=7)

root.mainloop()
