---
layout: post
title:  "How to Setup SSH on GitHub"
date:   2023-02-18 
categories: GitHub, SSH
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

![GitHub Account](https://cvws.icloud-content.com/B/AeVUdt9Chg0eNN52BazAfIy1sn2jAalRe44KU4u-nMx04qMuKPRxq8m7/Screenshot+2023-02-18+at+11.23.19.png?o=AtOlWpiFzsZTnpMZf_NM_m769d3skAdWSu4XrBdGYL0E&v=1&x=3&a=CAogINXAMmeIwxnI1UlqTf07-2mP6_3MdsFXzv-GyXbfkhgSbxChyvee5jAYoafToOYwIgEAUgS1sn2jWgRxq8m7aidK97w0pW9aTFuh_oTK1dMk6ao1PAwO0Frsc7EB-ISZwwx0I7p_ZydyJ_rE19z6CC245Ruz_PMTm-PSa2IGREI9P4F1AohZZxhY9izl2Lu5tg&e=1676716331&fl=&r=89b09a1c-cc26-444f-8978-81ce7d8ea0ae-1&k=0BecOEJhoC0woBp_z75XXA&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=32&s=zX3jayfoTXk8OSgAtXjS3Syss7I&cd=i)

You can then on the left find the SSH and GPG Keys:

![enter image description here](https://cvws.icloud-content.com/B/AdJSibs71ynIMrDDnDs4AN9e84CoAWKPXU-gH-CSRjjx_lMOueP27P44/Screenshot+2023-02-18+at+11.33.17.png?o=AjmQmsKKdMkmmFhwBziA9hFe-MJHOdDfJOb14JZmgYG3&v=1&x=3&a=CAogd4m_DmBqFaGqrXr0s1c2qfOfnGjA-Qz4sRFRJV6aMlwSbxCX8Ief5jAYl83joOYwIgEAUgRe84CoWgT27P44aifvN4hbEab1sCBNul0e_9zDm06dYjQ4Br1SUp7hHweJ6e_hkGBFhNVyJ6yawv2cA4cmUoe1UU5yeucf7lw-pXdf2rVKjdWtWeRXRReh8Uz4XQ&e=1676716598&fl=&r=8c8052b8-1f74-4698-b3fe-6f14706a9058-1&k=_069zKmrpNJz1t8084DwDQ&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=32&s=oIK0pIYjB4fMecnqr_a0fq4yyI4&cd=i)

Once there Click on the `New SSH Key`:

![enter image description here](https://cvws.icloud-content.com/B/Aa7a4HotCt1awuCLtT47qr5LPZJEAW0tsFTJHhliVTPdvjZmV4S9NmDM/Screenshot+2023-02-18+at+11.33.30.png?o=Agb-ALAHqhiw4oFUP7oVB7d-YUIUvZun4buJtWA0p7QG&v=1&x=3&a=CAogDX9hUkqzzW5MkH4s39g2LZFsTCDNL1YPx0XbQ8jmXFgSbxC2146f5jAYtrTqoOYwIgEAUgRLPZJEWgS9NmDMaie9DkzuQmq4vZEOGkGkN22nCi3Cp8Llq8kRdVi8C_KxR7jnMjfBDRFyJ2GwLv5CLQ8KHGE6p_EkRZKdBlANR-y08tpVaGlgkvTX5Zn8reRT1g&e=1676716710&fl=&r=5ed68553-3360-4467-b42e-91418023b2d6-1&k=Rp9bKsLVcixs1fhfmPAuow&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=32&s=RNS5q73dA8yv00_5wxQcuGMWW4U&cd=i)

And you can then Copy & Paste the value you outputed previously:

![enter image description here](https://cvws.icloud-content.com/B/AZQ1rW_xNzM8IG6SH2lu-Oe_r3qlAf-rCmouM6VEJPWfTDggqKG0qlkE/Screenshot+2023-02-18+at+11.34.00.png?o=AsEbCr-RpUbJ9JdtazpIhr64P05YhjyP8Xo7dHnVaHgF&v=1&x=3&a=CAognbZPJvRvc40AZ_JLPtavEF2pUyZF2InfeHwyGOEZxE8SbxCqhpOf5jAYquPuoOYwIgEAUgS_r3qlWgS0qlkEaidCo3hCJ-ZFJU34EjG64ZjF3OP1A-0cCkbf0RPyzgUfIvcU-mK0EWhyJ95IXr9HHfFH77GEZfC8TXRZg_TEJr5tGG_VTd5-I07IVLHgNz81Gw&e=1676716781&fl=&r=4cbe1ce7-bf1b-467d-91f2-add763a55d1d-1&k=xEU83y7yOm4LoV5PyABqWw&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=32&s=0eRMZ21l1gu_DNd59mfPLQAc4e0&cd=i)

And you can then click `Add SSH Key`, this might prompt you some MFA code or password input, that's fine.

After all this is done you can now use SSH with you Repos

## Cloning a Repo
Once you are done you can go to any repo you want and add select the SSH value instead of HTTPS:

![enter image description here](https://cvws.icloud-content.com/B/ASPTfi2uqJsrmhMhKbux9pQA2HFUAaO2e9zdTM4KsssxH2QFoGyNAKUS/Screenshot+2023-02-18+at+11.35.40.png?o=AsHvp3VoXaCln87lQLtUiNJ3UBKoqIkr47aRV626bmOU&v=1&x=3&a=CAogldrDTZQjxEBsqTHMEPPjKTH9WSByPV0DFos7DtUmmtgSbxD_tpuf5jAY_5P3oOYwIgEAUgQA2HFUWgSNAKUSaicFLVevHbFnDmMibaooar4FJBBoYVVj48bEiiRP_ezPoz5XyTM9KqdyJ2fjlichksG71u-JZOEdgED4-CRmbOfWSwWi9Yqn_lBeLhCRTA-ewg&e=1676716919&fl=&r=953fa7c1-9ee4-45c0-b8ca-dc8154b40fcd-1&k=100nUyA6Du5iXYke3h2v_A&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=32&s=vaGTJo_7vCMg6EEEO3Kw_HTLLPI&cd=i)

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
