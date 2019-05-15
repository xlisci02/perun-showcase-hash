# perun-showcase-hash

```
# clone
git clone https://github.com/xlisci02/perun-showcase-hash
cd perun-showcase-hash

# build and run
make
time ./regex seed.txt
time ./regex worst-case-muts/worst_case2.txt

# to fuzz, first initialize as perun repo
perun init --vsc-type=git --configure

# create output directory for fuzzing
mkdir output

# fuzz example
perun fuzz -b ./wordcount -w seed.txt -o output -t 900 -N 1000000 -mcs unitary
```
