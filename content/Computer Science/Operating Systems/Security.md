- controlling access of processes + users to system resources
- defense of system against internal and external attacks (firewall)
- assign permissions

- user identifier
- group identifier


## Dual Mode
Allows OS to protect itself and other system components, distinguished by the **mode bit**
**Kernel Mode** 
**User Mode**

![[Pasted image 20241115150547.png]]

>[!INFO] Practical
**privilege escalation** - allows user to change their effective ID to gain enhanced permissions: `sudo rm file`

>[!INFO] Practical
>When setting the **setuid** bit, the process temporarily adopts **UID** of the file's owner

