# SafeOpener 1

Given a java program which asks for a password and checks it with an encoded base64 version

the program flow :-
reader the password from the user
encode the password to base64 

compare it with a base64 stored in the program call it x
so we need the plain text that matches the x

decode the x and we can find the flag which is actually the decoded one

note to compile a .java file 
javac file_name.java 
# generates a .class file
to run 
java file_name
# SafeOpener 2

given a .class it is a corrupted file and cause run time error
to get additional info we can decomile it for this, use javap
javap -c class_name.class

the flag was visible in the decomplied output