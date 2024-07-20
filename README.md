# Linux

### Certifications

#### [Red Hat Certified Server Administrator](https://www.redhat.com/en/services/certification/rhcsa)

### Concepts

#### [Getting Help](/concepts/Help.md)
#### [Input and Output Redirects](/concepts/InputOutputRedirects.md)
#### [File Management](/concepts/FileManagement.md)
#### [Pipes](/concepts/Pipes.md)
#### [Text Editors](/concepts/TextEditors.md)


## User Account Management

You can use the following:

- `useradd`
- `groupadd`
- `userdel`
- `groupdel`
- `usermod`

You can check if a user is created with `id username`, you can also check to see if it created a home directory for that user.

### Switching Users

You can switch user with `su`, this is in the format `su - username`.

## SSH with Keys

You can set up keys to allow SSH with keys rather than providing a username and password.

To do this, you create keys on the host machine and run a commmand to copy them across to the remote machine.

```bash
# on the host machine, generate the keys
ssh-keygen

# copy the key across
ssh-copy-id root@123.123.123.123

# login
ssh root@123.123.123.123
ssh -l root 123.123.123.13
```
