# Array-Manupulation
# Hacker Rank

#!/bin/python3

import math
import os
import random
import re
import sys

#
# Complete the 'arrayManipulation' function below.
#
# The function is expected to return a LONG_INTEGER.
# The function accepts following parameters:
#  1. INTEGER n
#  2. 2D_INTEGER_ARRAY queries
#

def arrayManipulation(n, queries):
    quesries_count = len(queries)
    list_b = [0]*(n+2)
    for a,b,k in queries:
        list_b[a] += k
        list_b[b+1] -= k

    maxsum = 0
    temp = 0
    for val in list_b:
        temp += val
        maxsum = max(maxsum,temp)
    return maxsum
        
    
    # list_a = []
    # for i in range(n):
    #     list_a.append(0)
    # for i in range(quesries_count):
    #     in1,in2,value = queries[i]
    #     for j in range(in1-1,in2):
    #         list_a[j]=list_a[j]+value
    #     # print('queries'+str(i)+str(queries[i]),str(list_a))
    # return max(list_a)
            
        
        
        
        
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    first_multiple_input = input().rstrip().split()

    n = int(first_multiple_input[0])

    m = int(first_multiple_input[1])

    queries = []

    for _ in range(m):
        queries.append(list(map(int, input().rstrip().split())))

    result = arrayManipulation(n, queries)

    fptr.write(str(result) + '\n')

    fptr.close()

