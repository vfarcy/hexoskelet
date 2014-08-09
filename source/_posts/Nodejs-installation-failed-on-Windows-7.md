title: 'Nodejs installation failed on Windows 7'
date: 2014-08-04 08:32:13
tags:
---

I just installed Nodejs on a computer with windows seven and can't get npm to work on it,although the node server starts perfectly.

If I enter : 

`npm install` 

it gives me :

    Error : ENOENT, stat 'C:\Usesrs\User\Appdata\Roaming\npm'

I googled stackoverflow and found out that someone had the same issue on windows 8. He was answered the root cause was a missing `npm` folder.  

So I created a `npm` folder in the `'C:\Usesrs\User\Appdata\Roaming\'` and everything worked fine.

This is a strange error that didn't occur on my previous Nodejs installations. I don't understand why the installation process didn't create it this time, it seems like a bug in latest NodeJS windows installation.

