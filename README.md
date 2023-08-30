# screendump
This will tell you how to fix screendump iOS 14+

### step 1

Install the followings:

1. ldid
2. curl
3. libplist3
4. screendump

### step 2

run this in mobile using newterm or ssh:

curl https://raw.githubusercontent.com/hg13bs/screendump/main/entitlements.plist -o entitlements.plist && ldid -Sentitlements.plist /usr/libexec/screendumpd

### step 3

congrat bug fix !!!11 it should work now

### code explanation

"curl https://raw.githubusercontent.com/hg13bs/screendump/main/entitlements.plist -o entitlements.plist"

This code crawls to the defined url and this part "-o entitlements.plist" saves the file as entitlements.plist to the current directory (it will overwrite the file if it exists so make sure you have that other entitlements file saved)

"ldid -Sentitlements.plist /usr/libexec/screendumpd"

This code signs the screendump daemon with the correct entitlements obtained from the referenced file using ldid (in this case it's entitlements.plist)

## faq

# Library not loaded: /usr/lib/libplist.3.dylib

If you get this error then reinstall ldid/libplist3

Sometimes ldid references the wrong libplist library, if it doesn't work, try reinstalling libplist3

# curl: (23) failure writing output to destination

If you get this error then it means it failed saving the entitlements.plist to the current directory on the terminal, try cd to a different directory

# ldid.cpp(2178): assert(): open: /usr/libexec/.ldid.screendumpd

I don't know what this error means but probably try rerunning the ldid command again