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

**Step 1 :**
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


**References:**

[1] [How to Create an SSH Key in Linux: Easy Step-by-Step Guide](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server)

## 2. SSH passphrase protected key based login