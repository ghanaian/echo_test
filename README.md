# echo_test
debian package for echo message "this is a test from Hua Guo" in both install and execution
Fails of adding patch to add and install testing.sh 
Successful to echo "this is a test from Hua Guo" in apt install


1) create patch file diff
diff -Naur hello-2.10/src/ hello-2.10.modify/src/ >test.patch
2)  create debian directory using bzr dh-make
bzr dh-make hello 2.10 hello_2.10.orig.tar.gz
3) customize changelog control  rules in debian directory
4)  add test.patch to debian/patches
5)  add debian/install for installing src/testing.sh     // error here, temporary fix by comment out this
6) build the package 
	bzr builddeb -- -us -uc

Reference:
Ubuntu Packaging Guide
https://packaging.ubuntu.com/html/packaging-new-software.html

Ubuntu maintainers handbook
https://github.com/canonical/ubuntu-maintainers-handbook

MaintainerScripts
https://wiki.debian.org/MaintainerScripts

Guide for Debian Maintainers
https://www.debian.org/doc/manuals/debmake-doc/debmake-doc.en.pdf
