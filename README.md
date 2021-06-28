# PAM

## Setup
```
sudo apt install libpam0g-dev
```

## Compile
```
gcc -fPIC -fno-stack-protector -c pam.c
```

## Add to dir with pam modules
```
sudo ld -x --shared -o /lib/x86_64-linux-gnu/security/pam.so pam.o
```
## Update file /etc/pam.d/login
```
# Standard Un*x authentication
@include common-auth
auth required pam.so
```
