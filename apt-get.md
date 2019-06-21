# apt-get apt-key apt-cache 
## How apt-get works
The following links says details about the apt-get. Some important information has been copied 
[apt-get ](https://askubuntu.com/questions/131397/what-is-a-repository-key-under-ubuntu-and-how-do-they-work)

> `Apt-get` package management uses public key cryptography to authenticate downloaded packages.
> 
> -   Debian does an excellent job of explaining Secure apt on this wiki page.
> 
> What follows is a short summary of the key acquisition and verification process gleaned from Debian's wiki page.
> 
> Basic Concepts Public key cryptography is based on pairs of keys, a `public key` and a `private key`. The `public key` is given out to the world; the `private key` must be kept a secret. Anyone possessing the public key can encrypt a message so that it can only be read by someone possessing the private key. It's also possible to use a private key to sign a file, not encrypt it. If a private key is used to sign a file, then anyone who has the public key can check that the file was signed by that key. No one who doesn't have the private key can forge such a signature.
> 
> gpg (GNU Privacy Guard) is the tool used in secure apt to sign files and check their signatures.
> 
> apt-key is a program that is used to manage a keyring of gpg keys for secure apt. The keyring is kept in the file `/etc/apt/trusted.gpg` (not to be confused with the related but not very interesting `/etc/apt/trustdb.gpg`). apt-key can be used to show the keys in the keyring, and to add or remove a key.
> 
> Each time you add another apt repository to `/etc/apt/sources.list`, you'll also have to give apt its key if you want apt to trust it. Once you have obtained the key, you can validate it by checking the key's fingerprint and then signing this public key with your private key. You can then add the key to apt's keyring with `apt-key add <key>`
## 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI1MTA1MzMyOCwtMTc0MzQ2NDQ2OV19
-->