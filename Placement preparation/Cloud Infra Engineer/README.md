# Cloud Infrastructure Engineer

## 1. SSH key based login

**SSH (or Secure SHell)**

- SSH is an encrypted protocol used to administer and communicate with servers.
- While working with Linux servers, our most of the time spend in a terminal session connected to your server via SSH.
- Using SSH key provides a secure way (also recommened) for logging into your server.


**How Do SSH Keys Works**

- SSH keys pairs are two cryptographically secure keys that can be used to authenticate a client to an SSH server.
- Each key consistes of a _**Public key**_ and a _**Private key**_.
- The **Private key** is retained by the clinet and should be **kept absolutely secret**. If compromised, the private key will allow any hackers to access the server configured with associated Public key without any additional authentication. (For additional precaution, the private key can be encrypted on a disk with a paraphrase)
- The associated **Public key** can be shared freely. The public key is used to encrypt message that only a provate key can decrypt.
- The Public key is uploaded to a remote server thet you wnat to access using SSH.
- The key is added to a special file within the user account you will be logging into called `~/.ssh/authorized_keys`.
- When a client attempts to authenticate using SSH keys, the server can test the client on whether they are in possession of the private key. If the client can prove that it owns the private key, a shell session is spawned or the requested command is executed.

**Step 1 (Creating SSH Keys)**
- The first step to configure SSH key authentication to your server is to generate an SSH key pair on your local computer. This can be done using a utility`ssh-keygen`. By default this will create a 3072 bit RSA key pair. 
- The utility will prompt you to select a location for the keys that will be generated.
- Next, you will be prompted to enter a passphrase for the key. This is an optional passphrase that can be used to encrypt the private key file on disk, for additional security.
- The output will look like:

```
OutputYour identification has been saved in /home/username/.ssh/id_rsa.
Your public key has been saved in /home/username/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:CAjsV9M/tt5skazroTc1ZRGCBz+kGtYUIPhRvvZJYBs username@hostname
The key's randomart image is:
+---[RSA 3072]----+
|o   ..oo.++o ..  |
| o o +o.o.+...   |
|. . + oE.o.o  .  |
| . . oo.B+  .o   |
|  .   .=S.+ +    |
|      . o..*     |
|        .+= o    |
|        .=.+     |
|       .oo+      |
+----[SHA256]-----+
```

** Step 2 (Copying an SSH Public Key to Your Server)**

- Copy the content of `id_rsa.pub` to a file at `~/.ssh/authorized_keys` on your remote machine somehow.
- You can use the command : `cat id_rsa.pub` in the client machine (or local machine).
- You will see the key’s content, which may look something like this:
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCqql6MzstZYh1TmWWv11q5O3pISj2ZFl9HgH1JLknLLx44+tXfJ7mIrKNxOOwxIxvcBF8PXSYvobFYEZjGIVCEAjrUzLiIxbyCoxVyle7Q+bqgZ8SeeM8wzytsY+dVGcBxF6N4JS+zVk5eMcV385gG3Y6ON3EG112n6d+SMXY0OEBIcO6x+PnUSGHrSgpBgX7Ks1r7xqFa7heJLLt2wWwkARptX7udSq05paBhcpB0pHtA1Rfz3K2B+ZVIpSDfki9UVKzT8JUmwW6NNzSgxUfQHGwnW7kj4jp4AT0VZk3ADw497M2G/12N0PPB5CnhHf7ovgy6nL1ikrygTKRFmNZISvAcywB9GVqNAVE+ZHDSCuURNsAInVzgYo9xgJDW8wUw2o8U77+xiFxgI5QSZX3Iq7YLMgeksaO4rBJEa54k8m5wEiEE1nUhLuJ0X/vh2xPff6SQ1BL/zkOhvJCACK6Vb15mDOeCSq54Cr7kvS46itMosi/uS66+PujOO+xt/2FWYepz6ZlN70bRly57Q06J+ZJoc9FfBCbCyYH7U/ASsmY095ywPsBo1XQ9PqhnN1/YOorJ068foQDNVpm146mUpILVxmq41Cj55YKHEazXGsdBIbXWhcrRf4G2fJLRcGUr9q8/lERo9oxRm5JFX6TCmj6kmiFqv+Ow9gI0x8GvaQ== username@hostname
```
- Now you can add the contents of your `id_rsa.pub` file to the end of the `authorized_keys` file in the `~/.ssh` directory using the below command (Replace `public_key_string` with the output from the `cat ~/.ssh/id_rsa.pub` you executed on the client/local machine):

```
echo public_key_string >> ~/.ssh/authorized_keys
``` 

- __If you stored keys in a different path please remember it. It will be used for authentication:__


** Step 3 (Authenticating to Your Server Using SSH Keys)**

- If you did not change the default path while generating ssh keys, the use the below command to login:
```
ssh username@remote_host
```

- Else use the below command:
```
ssh -i <path_to_keys> username@remote_host
```


**References:**

[1] [How to Create an SSH Key in Linux: Easy Step-by-Step Guide](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server)

## 2. SSH passphrase protected key based login