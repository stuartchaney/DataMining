Collaborative Filtering Sample
===============================

Item-item Recommendation using Tanimono(Jaccard) Coefficient.

There are rewritten versions of the codes in 2nd Chapter of 
Programming Collective Intelligence ( http://oreilly.com/catalog/9780596529321/ )
By Toby Segaran, O'Reilly Media, ISBN: 978-0-596-52932-1.

License
--------------

GNU GENERAL PUBLIC LICENSE Version 3 (or any later version).

File Formats
--------------

Input
######

user_id,item_id,item_id.....

Example
^^^^^^^
XXX,10003034161186,10002834941181
YYY,10002835301181,10002802701186,10002812981181,10002820141181,20664208510938,10003039991181,10002812171181

Output
#######

item_id:score|item_id,score|item_id...

Example
^^^^^^^

10001946891177:0.16|10003125591177,0.1|10003297171177,0.08|10003294401177,0.0769231|10002827001177,0.0769231|10003258030989,0.0769231|10003208731177,0.0769231|10002884920113,0.0769231|10003340900769,0.0769231|10003121840813,0.0769231|10002308561176,

Programs
--------


StandAlone
##########

https://github.com/haruyama/DataMining/tree/master/CollaborativeFiltering/C++/item-item5

./main <  users.csv > output

Performance
^^^^^^^^^^^
I used Intel(R) Core(TM) i7 CPU 920  @ 2.67GHz.

120000 users and 280000 items: about 80 minites 

Using MPI
#########

https://github.com/haruyama/DataMining/tree/master/CollaborativeFiltering/C++/mpi3

::

  rm output.*
  mpirun -np 6 ./main -stdin 0  <  users.csv
  cat output.* | sort output


Performance
^^^^^^^^^^^
I used Intel(R) Core(TM) i7 CPU 920  @ 2.67GHz.

120000 users and 280000 items | 6 processes (1 control process and 5 calcurating processes.): about 20 minites
