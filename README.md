# CodeCollectionForCalculation #
collect the high-frequency codes for calculation program

## brief structure ##
### imoprt
### read
### pre-cessor
### calculation
### suf-cessor
### result_save
### main

### import ###
import numpy as np
import pandas as pd
import matplotlib as mlp # use for agg.path.chunksize
import os,sys
import math
from nptdms import TdmsFile
from matplotlib import pyplot as plt


### read data ###
DataX=pd.read_csv('FileName.csv') #read data via pandas

TdFile=TdmsFile('FileName.tdms') #read data via TdmsFile, for tdms file, need to figure out the index to know the group/channel info.
PWM=TdFile.object("PWM","cDAQ2Mod2/ai0").data
Analog=TdFile.object("Analog","cDAQ2Mod3/ai0").data*20 
Angle=TdFile.object("Encoder","cDAQ2Mod3_1/ctr0").data


#--------------precessor---------------------
DataA=pd.DataFrame(DataNdarray)#convert DataNdarray from ndarray to pandas DataFrame.
DataX.dropna(how='any')#drop the row contains NaN
DataX.filna(value=0)#replace the NaN with value
DataX=pd.drop([0,1])#dele the row1 and row2
DataY=DataX.astype('float')# convert the str to float if necessary

DataX.columns[1,2,3]#rename the columns label to [1,2,3]
DataX.columns=range(1,n+1)#create the column labels[1,...,n]
DataX.index=NameList #add the tags for rows. NameList is list type[a,b,c,d,...]

DataX.sort_values(by=[n,n-1],ascending=True)# Mainly sort acc. to column_n ，second sort acc. column_n-1
DataX.drop_duplicates(subset=n,keep='first')# drop acc. to column_n, dele the duplicated rows, keep the first row.
DataZ[4]=listX# listX is a list like data [1,2,3,...], create the column_4
DataZ[4]=DataZ[1]+DataZ[2]#create the column_4, and the value is column_1+column_2.  operation including '+ - * / ' is supported; If math module is involved, only number is accepted.

listX=5*[0]+listY# [0,0,0,0,0,1,2]=5*[0]+[1,2]
listC=list(zip(listA,listB))# combine the two list and return a object. convert to list to get a tuple [(a1,b1),(a2,b2),(a3,b3),...]
listC.append(element)# add element to listC

#------------------------------------calculation---------------
math.atan(y/x)#output the ArcAngle between vector(x,y) and (0,1)
math.atan2(y,x)#output the ArcAngle between vector(x,y) and (0,1)
math.sqrt(x)
math.degrees(AcrAngle)# convert the AcrAngle to degrees

#--------------------------sufcessor----------------------
print('%0.3f any texts %0.3f'%(num1,num2))#字符串格式化，保留三位小数，输出两个数字，依次对应括号中num1和num2

plt.figure(figsize=(10,20))# define the plot area as 100x200 pixles
plt.subplot(1,2,1)#1st block of two blocks
plt.plot(x,y)#plot a single x-y curve drawing,
plt.plot(x,y,x,z)#plot two curves in one drawing
plt.axis([Xmin,Xmax,Ymin,Ymax])#define the range for x and y axis
plt.ylabel('PWM')
plt.xlabel("TravelAngle°")
plt.title('info_summary')
plt.text(1,1.5,'Correlation',size=10)#show extra texts'Correlation' in the drawing, postion pixles(10,15),fontsize=10
plt.grid(True)# show the grids in the drawing background
LabelPWM= ['MeasuredPWM', 'Theoritical']#Name for multi-curves Legend
plt.legend(LabelPWM, loc='upper left')#show legend and location
plt.show()#show drawing via a pre-defined window with some powerful and useful tools.

#----------------------------------------result save-------------------------
plt.savefig('./Report/%s.jpg'%DataName)#save the drawing, if there is no File named 'Report',create a new File "Report" under current File.
np.savetxt('datax.csv',DataX,delimiter=',',header='1,2,3,4,5,6,....')#save the dataX to datax.csv, and add a header for each column,'1,2,3...'divided by delimiter.
DataX.to_csv('./Report/summary.csv') #save the DataX to a excel.

#---------------------------------------main--------------------------
if __name__=='__main__':
    print('\n\n\n'+'>>>>>>Pedal Function Test | Angle-Signal Analysis<<<<<<<'+'\n\n\n')
    DataName=input('input the FileName XXXX.tdms,Press ENTER twice to Confirm input  :) \n')

    while DataName.lower() not in ['quit']:# this 'while' is to check whether the input is a 'FileName' or 'quit request'
        while DataName not in os.listdir(): #this 'while' is to check if input DataName exits or not.
            DataName=input('FileName is not existing, Try Again Pls.>>> XXX.tdms<<<  :( \n')
        main(DataName)
        DataName=input('\nWell Done ,Ready for next round ,PLease input the FileName XXXX.tdms,  :) \n')
    print('Mission Completed') #complete the exe program and exe.close
