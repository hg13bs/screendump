# screendump
eh idk this will tell you how to fix screendump iOS 14+

### step 1

need curl + ldid + screendump from julioverne repository

### step 2

run this in mobile using newterm or ssh:

curl https://raw.githubusercontent.com/hg13bs/screendump/main/entitlements.plist -o entitlements.plist && ldid -Sentitlements.plist /usr/libexec/screendumpd

### step 3

congrat bug fix !!!11 it should work now
