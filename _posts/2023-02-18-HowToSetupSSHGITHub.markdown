---
layout: post
title:  "How to Setup SSH on GitHub"
date:   2023-02-18 
---

# How to setup SSH key for Github

> This will focus on macOs/Linux operating systems

## Generating a SSH key

On unix operating systems the ssh keys that you generate will generally be in the *.ssh* folder.
To get to the folder use the following command:

    $ cd ~/.ssh

Once you are inside the folder you can now generate the SSH key:

    $ ssh-keygen -o -t rsa -C "{your@email.com}"

This will prompt you where to save the file, since we want it in this folder just hit `return`

It will then prompt you for a passphrase which isn't necessary, (if you want to add it that's fine), just hit `return`
Will then prompt for confirmation, just hit `return`

It should return the following
```
The key fingerprint is:
SHA256:NnATrRJrSpO1nIjhekAd2uvcfsRBVIoBec9O+5ezyRk example@example
The key's randomart image is:
+---[RSA 3072]----+
|  .o+...oo       |
| .+o .=....      |
|.o +.*=*o.       |
|. o * BB..       |
| o o ++.S        |
|. + o  * .       |
| . o .. .  E.    |
|    .  . ..++    |
|     ..   .=o    |
+----[SHA256]-----+
```
You can verify that it generated a key by using the following command:
```
$ cat id_rsa.pub

=== Output ===
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCfqFBsoAoCVRxRSrUjCKK0Rb1Y+siJwCuuPdELgBgS2v7PO8av3tOFkvXMcr5SSw+02AP2LtqcC/jf9q31ppN0NmzZrysvifG8LxEdmjYvcU28PlgneQ+1Dambno6pmxhDWjTbMscVwVhJzy1kYkTJ4205YC9LBgPLRggLps6dJHdHAfM0pIN1j5SstRt3gyOQKX1VZovM1212ENYttLDl6BC8xcUZLmdKZdIPEAJKjh13xro/iBk/S7EbP8EkNVrIkvIHvaEWxWk9KdOxRhv+h4FxFqf9qQy8sKP/yZtkFAjSrAULB8CFBFWfb9EGalJh4rWbTFCaMcM59Uz2Cie9Qna6BviGWnHX+/02ide3HYfFCa4F79LiikssdcS9XqK4x1KchrA0aQqLnBy/aixNfXO7FKPvKf5kKCbCWoxz3s2A0U1gZsK8mwqhd5H+yRgoKJNc/8ASxnb6gpGX7tUuamQrEjBw8Dn/dHckBHQ0kPl2wCCEViPR2Pk+rL75whk= example@example
```

Once you verified that the key is generated now we can add it to GitHub.

## Adding to GitHub

Once you have logged into you GitHub account, click on your Profile Image -> Settings:

![GitHub Account](https://res.cloudinary.com/thurling/image/upload/v1677831128/Blog%20Posts/How%20to%20Add%20SSH/Screenshot_2023-02-18_at_11.23.19_akdkud.png)

You can then on the left find the SSH and GPG Keys:

![enter image description here](https://res.cloudinary.com/thurling/image/upload/v1677831128/Blog%20Posts/How%20to%20Add%20SSH/Screenshot_2023-02-18_at_11.33.17_zvtiso.png)

Once there Click on the `New SSH Key`:

![enter image description here](https://res.cloudinary.com/thurling/image/upload/v1677831128/Blog%20Posts/How%20to%20Add%20SSH/Screenshot_2023-02-18_at_11.33.30_luynl9.png)

And you can then Copy & Paste the value you outputed previously:

![enter image description here](https://res.cloudinary.com/thurling/image/upload/v1677831128/Blog%20Posts/How%20to%20Add%20SSH/Screenshot_2023-02-18_at_11.34.00_fbtxia.png)

And you can then click `Add SSH Key`, this might prompt you some MFA code or password input, that's fine.

After all this is done you can now use SSH with you Repos

## Cloning a Repo
Once you are done you can go to any repo you want and add select the SSH value instead of HTTPS:

![enter image description here](https://res.cloudinary.com/thurling/image/upload/v1677831128/Blog%20Posts/How%20to%20Add%20SSH/Screenshot_2023-02-18_at_11.35.40_pdmrle.png)

Once you enter the SSH value, it will prompt you to add the SSH fingerprint you can just enter `yes` and hit `return`:

```
$ git clone git@github.com:Gl4SS3S/MyRepo.git

=========

Cloning into 'MyRepo'...
The authenticity of host 'github.com (140.82.121.3)' can't be established.
{Your_Value} key fingerprint is SHA256: {Your Fingerprint}
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
```

And you should be good to go!
Happy Coding.
