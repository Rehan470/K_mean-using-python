# K_mean-using-python
import numpy as np
arr = (np.array([42,22,11,37,21,19,22,23,35,36,32,31,27,24,12]))
a=float(input("Enter value of a"))
b=float(input("Enter value of b"))
f=True
count=0;
print("original array is",arr)
arr3=arr.copy()
while f !=0:
    c1=arr.copy()
    num=0
    i=0
    for i in range(len(arr)):
        c1[i]=a-c1[i]
        if(c1[i]<0):
            num=c1[i]
            c1[i]=abs(num)
    print("C1 is",c1) 
     
    c2=arr.copy()
    num=0
    j=0
    for j in range(len(arr)):
        c2[j]=b-c2[j]
        if(c2[j]<0):
            num=c2[j]
            c2[j]=abs(num)
    print("C2 is",c2)          
       
    count1=0
    count2=0
    sum_of_c1=0
    sum_of_c2=0
    k=0
    arr2=arr.copy()
    for k in range(14):
        if(c1[k]<c2[k]):
            sum_of_c1=sum_of_c1+arr[k]
            count1=count1+1
            arr2[k]=0;
        else:
            sum_of_c2=sum_of_c2+arr[k]
            count2=count2+1
            arr2[k]=1
            
    aa=(sum_of_c1/count1)
    bb=(sum_of_c2/count2)
    print(arr2)
    a=aa
    b=bb
    f=False
    l=0
    for l in range(len(arr)):
        if(arr2[l]==arr3[l]):
            f=True
        else:
            f=False
            break
    arr3=arr2
    count=count+1
print("After ",count,"Iterations it will be end")
