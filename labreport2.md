# Week 2 Lab Report

## Part 1

### Code for StringServer:
![Image](https://media.discordapp.net/attachments/776893122592112663/1069801032303001660/image.png)

### First Screenshot of using /add-message
![Image](https://media.discordapp.net/attachments/776893122592112663/1069802208796880977/image.png)

This is using the handleRequest(URI url) method. The relevant arguments to look at are the "s" right after the "?" in the url, which is parameters[0] in the code, and the argument after the "=" in the url, which is parameters[1] in the code. The relevant field to look at is String s, which concatenates parameters[1] along with \n (newline) whenever the /add-message?s=<string> is called.

### Second Screenshot of using /add-message
![Image](https://media.discordapp.net/attachments/776893122592112663/1069802310433259591/image.png)

This is very similar to the first screenshot. Both are using the handleRequest(URI url) method. The relevant arguments are still the same. The relevant field is still String s, which already contains the "Hello" from the first screenshot and is now concatenating parameters[1] along with \n (newline) from this screenshot after "=" in the url. This is why there is a newline between what we added in the first screenshot vs the second screenshot.


## Part 2

