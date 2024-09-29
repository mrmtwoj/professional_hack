![Logo](https://i.ibb.co/mbPkjss/image.png)                                                                           

## ProfessionalHack
- Mrmtwoj (Mohammad Javad Joshani)
- Life is full of moments you can learn from, but don’t just rush past them like I do.

# Finding Users with sh Based Shell
``` bash
cat /etc/passwd | grep 'sh$'

``` 
## Explanation:
cat /etc/passwd:
Displays the content of the /etc/passwd file. This file contains information about the system's users, including their usernames and default shells.
grep 'sh$':
Filters the output to show only the lines where the default shell ends with sh. The $ symbol indicates the end of a line, so this looks for shells like /bin/bash, /bin/sh, etc.

## Example Output:

``` bash
root:x:0:0:root:/root:/bin/bash
user1:x:1001:1001::/home/user1:/bin/sh

```
Use Case:
This command helps identify users who are using sh-based shells like bash, sh, or dash.

## Conclusion
These two commands are useful for system administrators to manage and secure Linux systems:
The first command helps identify files with SUID permissions, which can pose security risks if not handled properly.
The second command lists users with sh-based shells, helping in user management tasks.



# Finding Files with SUID Bit Set

```bash
find / -perm -4000 2>/dev/null

```
This section describes the use of a Linux command to locate files that have the SUID (Set User ID) bit set, which can pose security risks if misconfigured.
## Description:
```bash
find /:

```

This part of the command initiates a search from the root directory (/), scanning the entire file system for files.
```bash
-perm -4000:

````

This option specifies that the command should look for files with the SUID bit set. The SUID bit allows users to execute a file with the permissions of the file owner, potentially leading to privilege escalation if misused.
```bash
2>/dev/null:

```
This redirects any error messages (such as "Permission denied" when trying to access restricted directories) to /dev/null, effectively ignoring those errors and keeping the output clean.

## Use Case:
This command is commonly used by system administrators to identify files with sensitive permissions that may pose security risks. Files with the SUID bit can be exploited if they are not properly secured.

## Example Output:
The output will list files with the SUID bit set, which might look like this:

```bash
/usr/bin/sudo
/usr/bin/passwd

```
## Conclusion:
Regularly checking for files with the SUID bit set is an important practice in maintaining system security. This command helps identify potential vulnerabilities that need to be addressed.

