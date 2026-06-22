81% of storage used … If you run out, you can't create, edit and upload files. Get 30 GB for ₹15 for 3 months ₹59.

1

100%

import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

import time

Main\_Menu='''

&#x20;         -----MAIN MENU-----

&#x20;         1)Market share data analysis Import to dataframe or

&#x20;         Export to CSV file.

&#x20;         2)Market share Data Analysis/Data Manipulation.

&#x20;         3)Market share Data Visualization.

&#x20;         4)Exit.'''

plot\_menu=''' -----PLOT MENU-----

&#x20;         1)Line plot Company Vs Target Price and Common Market Price

&#x20;         2)Bar Graph showing Sum of Target Price Share Type Wise

&#x20;         3)Barh Company Vs Target Price

&#x20;         4)Histogram of Common Market Price, Target Price, Realized Returns

&#x20;         5)Return to Main Menu'''

Analysis\_Menu='''  -----SEARCH/ADDITION/DELETION-----

&#x20;             1)Display all records.

&#x20;             2)Search records based on Selected columns.

&#x20;             3)Search records based on Type.

&#x20;             4)Search records based on Row label/Number(loc\[],iloc\[]).

&#x20;             5)Display details of share having maximum target price.

&#x20;             6)Display details of share having minimum common market price.

&#x20;             7)Top five records.

&#x20;             8)Last five records.

&#x20;             9)Addition of new record to the Dataframe.

&#x20;             10)Deletion of records from dataframe.

&#x20;             11)Adittion of New column Total Price to the dataframe.

&#x20;             12)Display dataframe information.

&#x20;             13)Display Description of the dataframe(Agrregate function).

&#x20;             14)Return to Main Menu.'''

import\_export\_menu=''' -----IMPORT/EXPORT MENU-----

&#x20;                  1)Import CSV to Dataframe.

&#x20;                  2)Export dataframe data to CSV file.

&#x20;                  3)Return to Main Menu.'''



while True:

&#x20;   print(Main\_Menu)

&#x20;   ch=int(input('Enter your choice'))

&#x20;   if ch==1:

&#x20;       while True:

&#x20;           print(import\_export\_menu)

&#x20;           ch3=int(input('Enter your choice'))

&#x20;           if ch3==1:

&#x20;               df=pd.read\_csv("F:/Projects XII-C 2023-24/Ritika-Simar   Shares Data/market share analysis.csv")

&#x20;               pd.set\_option('display.expand\_frame\_repr',False)

&#x20;               pd.set\_option('display.max\_rows',51)

&#x20;               print('Content of Dataframe')

&#x20;               print(df)

&#x20;               print()

&#x20;           elif ch3==2:

&#x20;               df.to\_csv('Market Share Analysis.csv',index=False,header=True)

&#x20;               print('Data Written in \[Market Share Analysis.csv] file')

&#x20;           elif ch3==3:

&#x20;               print('-----BACK TO MAIN MENU-----')

&#x20;               break

&#x20;           else:

&#x20;               print('WRONG CHOICE')

&#x20;   elif ch==2:

&#x20;       while True:

&#x20;           print(Analysis\_Menu)

&#x20;           ch1=int(input('Enter your Choice'))

&#x20;           if ch1==1:

&#x20;               print(df)

&#x20;               print()

&#x20;           elif ch1==2:

&#x20;               print('List of columns are')

&#x20;               for x in df.columns:

&#x20;                   print(x,end=',')

&#x20;               clist=\[]

&#x20;               print()

&#x20;               while True:

&#x20;                   c=input('Enter your column name')

&#x20;                   clist.append(c)

&#x20;                   ch=input('Want to give more column names')

&#x20;                   if ch in 'nN':

&#x20;                       break

&#x20;               print('Details of selected columns')

&#x20;               print(df\[clist])

&#x20;               print()

&#x20;           elif ch1==3:

&#x20;               n=input('Enter Type name')

&#x20;               df1=df\[df.Type==n]

&#x20;               if df1.empty:

&#x20;                   print('Sorry NO data for this group')

&#x20;               else:

&#x20;                   print(df1)

&#x20;                   print()

&#x20;           elif ch1==4:

&#x20;               print('Available Records Number range',df.index)

&#x20;               n=int(input('Enter row number you want to display'))

&#x20;               df1=df.iloc\[n]

&#x20;               if df1.empty:

&#x20;                   print('NO RECORDS FOUND')

&#x20;               else:

&#x20;                   print(df1)

&#x20;           elif ch1==5:

&#x20;               df2=df\[df.Target\_Price== df.Target\_Price.max()]

&#x20;               if df2.empty:

&#x20;                   print('NO RECORDS FOUND')

&#x20;               else:

&#x20;                   print(df2)

&#x20;               print()

&#x20;           elif ch1==6:

&#x20;               df3=df\[df.CMP== df.CMP.min()]

&#x20;               if df3.empty:

&#x20;                   print('NO RECORDS')

&#x20;               else:

&#x20;                   print(df3)

&#x20;                   print()

&#x20;           elif ch1==7:

&#x20;               print('Top Five Records')

&#x20;               print(df.head())

&#x20;               print()

&#x20;           elif ch1==8:

&#x20;               print('Last five records')

&#x20;               print(df.tail())

&#x20;               print()

&#x20;           elif ch1==9:

&#x20;               br=input('Enter Company')

&#x20;               pr=input('Enter Broker')

&#x20;               ty=input("Enter Type")

&#x20;               nq=int(input('Enter BatchNo'))

&#x20;               c=int(input('Enter ShareNo'))

&#x20;               nos=int(input('Enter Target\_Price'))

&#x20;               cmp=int(input("Enter common market plaec"))

&#x20;               pf=float(input("Enter profit"))

&#x20;               rr=float(input("Realization return"))

&#x20;               df.loc\[51]=\[nq,br,pr,ty,c,cmp,nos,pf,rr]

&#x20;               print('RECORD INSERTED')

&#x20;           elif ch1==10:

&#x20;               n=int(input('Enter the row index to be deleted'))

&#x20;               print(df.drop(n,inplace=False))

&#x20;               print('RECORDE DELETED')

&#x20;           elif ch1==11:

&#x20;               df\['Total Price']= df.Profit\_Ptial + df.Target\_Price + df.Realized\_Returns

&#x20;               print(df\[\['Company','Broker','Total Price']])

&#x20;               print('COLUMN ADDED')

&#x20;           elif ch1==12:

&#x20;               print('DataFame Details')

&#x20;               print(df.info())

&#x20;               print()

&#x20;           elif ch1==13:

&#x20;               print('Descriptive Statistics')

&#x20;               print(df.describe())

&#x20;               print()

&#x20;           elif ch1==14:

&#x20;               print('BACK TO MAIN MENU')

&#x20;               break

&#x20;           else:

&#x20;               print('WRONG CHOICE')

&#x20;   elif ch==3:

&#x20;           while True:

&#x20;               print(plot\_menu)

&#x20;               ch2=int(input('Enter your choice'))

&#x20;               if ch2==1:

&#x20;                   company=df.Company

&#x20;                   cmp=df.CMP

&#x20;                   target=df.Target\_Price

&#x20;                   xdata=np.arange(len(company))

&#x20;                   plt.plot(xdata,cmp,marker='o',label="Common Market Price")

&#x20;                   plt.plot(xdata,target,marker='o',label="Target Price")

&#x20;                   plt.ylabel('Values',fontsize=12)

&#x20;                   plt.xlabel('Company Name',fontsize=12)

&#x20;                   plt.legend()

&#x20;                   plt.xticks(xdata,company,rotation='vertical')

&#x20;                   plt.title('Company wise Target Price and Common Market Price',fontsize=14)

&#x20;                   plt.subplots\_adjust(bottom=0.3)

&#x20;                   plt.show()

&#x20;               elif ch2==2:

&#x20;                   g=df.groupby('Type')

&#x20;                   s=g.Target\_Price.sum()

&#x20;                   plt.bar(s.index,s.values,color='r',label='Sum of Target Price')

&#x20;                   plt.ylabel('Sum of Target Price',fontsize=12)

&#x20;                   plt.xlabel('Share Type',fontsize=12)

&#x20;                   plt.title('Type Vs sum of Target Price')

&#x20;                   plt.legend()

&#x20;                   plt.subplots\_adjust(bottom=0.15)

&#x20;                   plt.show()

&#x20;               elif ch2==3:

&#x20;                   plt.barh(df.Company,df.Target\_Price,edgecolor='b')

&#x20;                   plt.ylabel('Company Name',fontsize=10)

&#x20;                   plt.xlabel('Target Price',fontsize=12)

&#x20;                   plt.title('Company Vs Target Price',fontsize=14)

&#x20;                   plt.subplots\_adjust(bottom=0.065)

&#x20;                   plt.show()

&#x20;               elif ch2==4:

&#x20;                   df\[\['CMP','Target\_Price','Realized\_Returns']].hist()

&#x20;                   plt.title("Analysis of CMP, Target \& Realized Returns")

&#x20;                   plt.show()

&#x20;               elif ch2==5:

&#x20;                   print('-----BACK TO MAIN MENU-----')

&#x20;                   break

&#x20;               else:

&#x20;                   print('WRONG CHOICE')



&#x20;   else:

&#x20;           for i in end\_msg:

&#x20;               print(i,end='')

&#x20;               time.sleep(0.0001)

&#x20;           break

&#x20;                      

