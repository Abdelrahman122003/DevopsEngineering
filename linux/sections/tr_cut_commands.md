> ## `tr` command

The tr command in Unix-like systems is used to translate or delete characters from the input data. It reads from standard input, processes the data according to the specified translation or deletion rules, and writes the result to standard output.

**Basic Syntax**

```s
tr [options] SET1 [SET2]
```

#### `Translate Characters`:

Replace characters in the input with corresponding characters from a specified set.

```s
echo "hallo world 123" | tr 'h' 'H'
# output is :
Hallo world
```

```s
echo "hallo world 123" | tr [:digit:] 'z'
# output is :
hallo world zzz
```

```s
echo "hallo world" | tr [:lower:] [:upper:]
# output is :
HALLO WORLD
```

#### `Delete Characters`:

Remove characters specified in the set from the input.

```s
echo "hello world" | tr -d 'o'
```

#### `Complement Character Sets`:

Apply translation or deletion to all characters not in the specified set.

```s
echo "hello world" | tr -c 'a-z' ' '
```

#### `Squeeze Repeated Characters`:

Replace sequences of a repeated character with a single instance.

```s
echo "hello world" | tr -s ' '
```

```s
cat file2.txt | tr -s 's','u','w'
```


## `cut` command

The cut command in Unix-like systems is used to extract specific sections or fields from each line of input data. It is commonly used for processing text files or command output.

**Basic Syntax**

```s
cut [options] [file...]
```

**Common Options:**

- `-f`: Specify the fields to extract (for delimiter-separated data).
- `-d`: Specify the delimiter to use for separating fields (default is TAB).
- `-c`: Specify character positions to extract.
- `-b`: Specify byte positions to extract (useful for binary data).


1. `Extract Specific Fields`:
   
    Extract the first and third fields from a colon-separated file.
    
    ```s
    echo "hallo world is this fucken world" | cut -d ' ' -f 1,3
    # The ouput is : hallo is
    ```
    
    ```s
    cut -d ' ' -f 1,3 filename.txt
    ```

2. `Extract Specific Characters`:
    
    Extract characters 1 to 5 from each line.

    ```s
    cut -c 1-5 filename.txt
    ```
3. `Extract Specific Bytes`:
   
   Extract the first 5 bytes from each line.

   ```s
   cut -b 1-5 filename.txt
   ```
4. `Extract Fields from Command Output`:
   
   Extract the first field from the output of the ls -l command.

   ```s
   ls -l | cut -d ' ' -f 1
   ```