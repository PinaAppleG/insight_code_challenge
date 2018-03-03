# Table of Contents
1. [Introduction](README.md#introduction)
2. [Instructions to run code](README.md#instructions-to-run-code)


# Introduction

This  repository contains the python solution for Insight Data Engineering Fellows program Coding Challenge.

My approach can be summarised as follows:

my program streams the input data line by line. For each line (record), my program check the validity of the record, ignore the record if there is any field invalid.

The program maintains two dictionary:

1. dict_donors: for each donor, record the ealiest date of contribution based on the data streamed so far;
2. dict_recipient: for each recipient at a particular year and a particular zip area, record the contribution from repeated donors.

After checking the validity of the input record, the program checks if the current record is from a repeated donor by comparing the transaction date with the recorded ealiest transaction date from this particular donor

If the current record is from a repeated donor, add this data entry to dict_recipient and prepare the output file.

Here I have made the assumption that if a donor contribute on the same day more than once, then the second contribution will be considered as 'repeat donation'

# Instructions to run code

The python code makes use of the libraries - numpy , sys and datetime 

Use ./run.sh command to run the code. The input is at ./input/itcont.txt and ./input/percentile.txt; the produced output is at ./output/repeat_donors.txt

Extra test suite provided in snsight_testsuite/tests/mytest_1  
