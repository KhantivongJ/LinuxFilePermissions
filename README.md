<h1> File permissions in Linux</h1>
<h2>Project description</h2>
Examine existing permissions on the file system. Determine if permissions match authorization that should be given. If not, modify permissions to authorize appropriate users and remove any unauthorized access.
<h2>Check file and directory details</h2>
Use <strong><em>ls -la</em></strong> to list all files in the current directory along with permissions.<br>
![CFDD](https://github.com/KhantivongJ/LinuxFilePermissions/blob/main/assets/CFDD.png)


<h2>Describe the permissions string</h2>
Permissions string is a set of 10 characters indicating the type of file as well as the permissions granted to the different types of owners; user, group, and others.<br><br>
<ul>
<li>First character indicates file type.</li>
<em><strong>d</strong>rwxr-xr-x</em><br><br>
<li>Next 3 characters indicate read, write, and execute permissions for Users</li>
<em>d<strong>rwx</strong>r-xr-x</em><br><br>
<li>Next 3 characters indicate read, write, and execute permissions for Group</li>
<em>drwx<strong>r-x</strong>r-x</em><br><br>
<li>Next 3 characters indicate read, write, and execute permissions for Others</li>
<em>drwxr-x<strong>r-x</strong></em><br>
</ul>

<h2>Change file permissions</h2>
The organization does not allow Others to have write permissions to files. Removed permissions from “project_k.txt” using<br><em><strong>chmod o-w project_k.txt</strong></em><br>
![Changing File Permissions](/assets/CFP.png)

<h2>Change file permissions on a hidden file</h2>
.project_x.txt, should not have write permissions for anyone but user and group should be able to read the file.

Used <strong><em>chmod u-w,g+r,g-w .project_x.txt</em></strong> to remove write permissions and add read permission.<br>
![Change File Permissions on a Hidden File](/assets/CFPHF.png)




<h2>Change directory permissions</h2>
Permission to the drafts directory should only be granted to the researcher2 user.
Used <strong><em>chmod g-x drafts/</em></strong> to remove unauthorized access to the drafts directory.<br>
![Change Directory Permissions](/assets/CDP.png)

<h2>Summary</h2>
The overall goal was to grant authorized users correct permissions and remove any unauthorized access from files. Using the chmod command, we limited the .project_x.txt file to read only for the user and group, removed access to the drafts directory for the group and others, and removed write permissions for others for all files. 
