# Perun fuzz demonstration on Java 1.1 String Hash Function

This is an example words counting program, which uses hash table with badly designed hash function used in Java 1.1 String Library. You can compare it to DJB hash function, but you have to comment/uncomment the particular lines in `hash_function.c` file. The project was created to demonstrate the functionality of [Perun](https://github.com/xlisci02/perun) fuzzing machine. 


## Clone the repository
First step is to clone this repository with following command:

    git clone https://github.com/xlisci02/perun-showcase-hash
    cd perun-showcase-hash

## Build and run for example with seed and mutation file
Notice the time difference between the runtime with initial seed and its mutation.

    make
    time ./regex seed.txt
    time ./regex worst-case-muts/worst_case2.txt

## Want to fuzz ? First initialize

Run the following and close the configuration file that pops up:

	perun init --vcs-type=git --configure

## Make sure your account's default identity is set
Run the following command to check your git settings:

	git config --list --show-origin

In case your identity is not defined, set your user name and email address like this

	git config user.email "you@example.com"
	git config user.name "Your Name"

## Finally, create output directory and start fuzz
The command for launching the fuzzing machine can look similar to this:

	mkdir output
    perun fuzz -b ./wordcount -w seed.txt -o output -t 900 -N 1000000 -mcs unitary

