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

### Failure inducing input for reversed method
``` java
public void testReverseLargerArray() {
  int[] input1 = {3, 4, 5};
  assertArrayEquals(new int[]{5, 4, 3}, ArrayExamples.reversed(input1));
}
```

### Non-failure inducing input for reversed method
``` java
public void testReversed() {
  int[] input1 = { };
  assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```

### Symptom of the tests above
![Image](https://media.discordapp.net/attachments/776893122592112663/1069814678512996373/image.png)
First test failed, second test passed

### Before and after reversed method

#### Before
``` java
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

#### After
``` java
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1]; //newArray[i] changed from arr[i] and arr[arr.length - i - 1] changed from newArray
  }
  return newArray; //changed from arr
}
```

This change fixes the issue because in the original code, the array arr is being assigned values from the array newArray, but newArray is just an array of zeroes the size of arr.length. Our fix assignes values from arr to newArray in reverse order, and returns newArray instead of arr.


## Part 3

Before week 2/3, I had no idea how to even begin in programming a webserver. These labs have helped me understand step by step how to start not only a web server, but also one that can have webpage outputs based on the inputs. This includes both performing math and also returning Strings.
