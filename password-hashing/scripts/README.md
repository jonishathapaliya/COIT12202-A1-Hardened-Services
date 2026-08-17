# Commands for Password Hashing
This folder contains all the commands used to configure and test password security

## PAM Password Quality
apt install libpam-pwquality
dpkg -l | grep libpam-pwquality

## Password Testing
passwd securitytest

## Account Lockout Testing
su - securitytest
