# File Permissions in Linux

## Project Description

The research team at my organization needed to update the file permissions for certain files and directories within the `projects` directory. The existing permissions did not reflect the appropriate level of authorization, which posed a security risk. To address this, I performed the following tasks:

---

## Check File and Directory Details

I used Linux commands to determine the existing permissions for a specific directory in the file system. Below is the command and its output:

```bash
researcher2@5d738f0f927b:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 .
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 ..
-rw-rw-rw- 1 researcher2 research_team   46 Dec  2 15:27 .project_x.txt
drwx------ 1 researcher2 research_team 4096 Dec  2 15:27 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Dec  2 15:27 project_k.txt
-rw-rw-rw- 1 researcher2 research_team   46 Dec  2 15:27 project_m.txt
-rw-rw-rw- 1 researcher2 research_team   46 Dec  2 15:27 project_r.txt
The ls -la command lists all contents of the projects directory, including hidden files.
```
The output shows:

One directory named drafts.

One hidden file named .project_x.txt.

Five other project files.

The 10-character string in the first column represents the permissions for each file or directory.

Describe the Permissions String
The 10-character permissions string can be broken down as follows:

1st Character: Indicates the file type.

d: Directory.

-: Regular file.

2nd-4th Characters: Permissions for the user (owner).

r: Read permission.

w: Write permission.

x: Execute permission.

-: Permission not granted.

5th-7th Characters: Permissions for the group.

Same as above (r, w, x, -).

8th-10th Characters: Permissions for others (all other users).

Same as above (r, w, x, -).

Example:
For the file project_t.txt with permissions -rw-rw-r--:

The first character (-) indicates it’s a file.

The user and group have read and write permissions (rw-).

Others have only read permission (r--).

No one has execute permissions.

Change File Permissions
The organization decided that others should not have write access to any files. To comply, I removed write permissions for others on project_k.txt:

```bash
researcher2@5d738f0f927b:~/projects$ chmod o-w project_k.txt
researcher2@5d738f0f927b:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 .
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 ..
-rw-rw---- 1 researcher2 research_team   46 Dec  2 15:27 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Dec  2 15:27 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_k.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_t.txt
```
The chmod o-w command removes write permissions for others.

The updated permissions for project_k.txt are now -rw-rw-r--.

Change File Permissions on a Hidden File
The research team archived .project_x.txt and wanted to ensure no one has write access, but the user and group should have read access. Here’s how I updated the permissions:

```bash
researcher2@5d738f0f927b:~/projects$ chmod u-w,g-w,g+r .project_x.txt
researcher2@5d738f0f927b:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 .
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 ..
-r--r----- 1 researcher2 research_team   46 Dec  2 15:27 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Dec  2 15:27 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_k.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_t.txt
```
u-w: Removes write permissions for the user.

g-w: Removes write permissions for the group.

g+r: Adds read permissions for the group.

Change Directory Permissions
The organization wanted only the researcher2 user to have access to the drafts directory. This meant removing execute permissions for the group:

```bash
researcher2@5d738f0f927b:~/projects$ chmod g-x drafts
researcher2@5d738f0f927b:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 .
drwxr-xr-x 3 researcher2 research_team 4096 Dec  2 15:27 ..
-r--r----- 1 researcher2 research_team   46 Dec  2 15:27 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Dec  2 15:27 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_k.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Dec  2 15:27 project_t.txt
```
g-x: Removes execute permissions for the group.
