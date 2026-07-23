rwx rwx rwx is read write execute in USer, group, other. Always have three sets. Then after are the names of the three groups: Caden, caden
If a d or a - at the beginning n(sometime san l) dash meansit is a file, d is a directory, l is a simlink
each has a patternn.
Each rwx has a 1 if it is on, and 0 if off. Then this translates to binary. 
to add execute permission: chmod u+X test.sh

chmod 600 test.sh is binary rep for 110 so certain permissions only for user

chown is used to set owner and group for a file
whoever process is created by is default owner. 