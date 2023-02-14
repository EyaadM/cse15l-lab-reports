# Week 3 Lab Report - Grep


## 1 - grep -l

This command lists the file that was located by grep without outputting where in the file the keyword was located. It is useful if you want to see a list of files that contain the keyword, for example.

### Example 1

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -l "Lucayans" written_2/travel_guides/berlitz2/*
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Here, we are able to see that only the path to the file located is outputted, not where in the file the keyword is.


### Example 2
```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -l "birds" written_2/non-fiction/OUP/*/*
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
```
Once again, only the paths are listed. Without the -l keyword, this output would be many more lines long, and we might have had to scroll up to see all of the files that had the keyword.

[Source](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)


## 2 - grep -r

The "r" stands for "recursive". This allows the grep commands to traverse through the directory selected to locate any files. This removes the need to use * and allows grep to search through nested directories.

### Example 1

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -rl "Lucayans" written_2
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Unlike the first time, we do not need to list the entire directory up to Bahamas-History.txt for grep to locate it, thanks to the -r option

### Example 2
```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -rl "birds" written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
```
Again, thanks to -r, we did not have to put /\*/\* for grep to locate these files. It is much more convienient to search for files this way.

[Source](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)



## 3 - grep -i

The "i" stand for "ignore-case". It's pretty self-explanatory. It's a grep that's not case sensitive. This makes it easier to search for keywords without needing to worry about case.

### Example 1

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -rli "lucayans" written_2
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Here, we can see that despite Bahamas-History only containing "Lucayans" with a capital L, the grep commands still locates it, thanks to the -i option.

### Example 2

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -rl "Birds" written_2/non-fiction/OUP

eyaad@LAPTOP:~/skill-demo1-data$
```

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -rli "Birds" written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
```
In the first code block, without the -i, grep cannot locate any of the files containing "birds" because the b in our word is capitilized. In the second code block, thanks to -i, the files are located even with the B being capitalized.

[Source](https://en.wikibooks.org/wiki/Grep)



## 4 - grep -c
This command line option lets you count the number of lines that contain the keyword in a file. This lets you see how often a keyword shows up in a file without scrolling through the file.

### Example 1

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -c "Lucayans" written_2/travel_guides/berlitz2/Bahamas-History.txt
2
```
This indicates that there are 2 lines containing "Lucayans" in this file.

### Example 2

```console
eyaad@LAPTOP:~/skill-demo1-data$ grep -c "birds" written_2/non-fiction/OUP/Berk/ch1.txt
1
```
This command shows us that there is only 1 line containing "birds" in this file.

[Source](https://man7.org/linux/man-pages/man1/grep.1p.html)
