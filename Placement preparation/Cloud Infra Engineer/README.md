# Cloud Infrastructure Engineer

## 2. SSH key based login

**SSH (or Secure SHell)**

- SSH is an encrypted protocol used to administer and communicate with servers.
- While working with Linux servers, our most of the time spend in a terminal session connected to your server via SSH.
- Using SSH key provides a secure way (also recommened) for logging into your server.


**How Do SSH Keys Works**

- SSH keys pairs are two cryptographically secure keys that can be used to authenticate a client to an SSH server.
- Each key consistes of a _Public key_ and a _Private key_.
- The **Private key** is retained by the clinet and should be **kept absolutely secret**. If compromised, the private key will allow any hackers to access the server configured with associated Public key without any additional authentication. (For additional precaution, the private key can be encrypted on a disk with a paraphrase)
- The associated **Public key** can be shared freely. The public key is used to encrypt message that only a provate key can decrypt.
- The Public key is uploaded to a remote server thet you wnat to access using SSH.
- The key is added to a special file within the user account you will be logging into called `~/.ssh/authorized_keys`.
- When a client attempts to authenticate using SSH keys, the server can test the client on whether they are in possession of the private key. If the client can prove that it owns the private key, a shell session is spawned or the requested command is executed.


**References:**
- [How to Create an SSH Key in Linux: Easy Step-by-Step Guide](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server)

## 2. SSH passphrase protected key based login