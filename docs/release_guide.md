# MoarVM Release Guide

## Versions

MoarVM currently has a monthly release cycle, with releases made in time for
the month's NQP and Rakudo release. Version numbers are simply YYYY.MM. For
example, the January 2014 release is 2014.01. If any bugfix releases need to
be made, they should be numbered as 2041.01.1, 2041.01.2, etc.

## Making a release

1. Make sure that you are on the MoarVM commit you want to make a release
   from, and that your status is clean.

2. Ensure that NQP and Rakudo will build and that `make test` in each is
   clean. Also run `make spectest` in Rakudo; discuss any failures you see
   with the Rakudo developers.

3. Update the VERSION file with the release name.

4. Run `make release VERSION=2014.01`, substituting the correct version name.

5. Take the .tar.gz file generated by step 4, copy it to a separate directory,
   extract it, and then in that directory do:
   
   perl Configure.pl --prefix=install
   make install
   install/bin/moar --version

6. Provided step 5 works, you have a release! Upload it, or ask on the MoarVM
   channel if you don't have access or know how to do that.

7. Do something fun to celebrate. Like watching nyan cat, or having a beer. Or
   why not both?