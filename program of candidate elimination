import csv
a=[]
csvfile=open('candiateliminationdataset.csv','r') 
reader=csv.reader(csvfile) 
for row in reader:
    a.append(row) 
    print(row)
num_attributes=len(a[0])-1 
print("Initial hypothesis is ") 
S=['0']*num_attributes 
G=['?']*num_attributes 
print("The most specific : ",S) 
print("The most general : ",G)

for j in range(0,num_attributes): 
    S[j]=a[0][j]
print("The candidate algorithm \n") 
temp=[]

for i in range(0,len(a)): 
    if(a[i][num_attributes]=='Yes'):
        for j in range(0,num_attributes): 
            if(a[i][j]!=S[j]):
               S[j]='?'
        for j in range(0,num_attributes):
            for k in range(1,len(temp)):
                if temp[k][j]!='?' and temp[k][j]!=S[j]: 
                   del temp[k]
        print("For instance {0} the hypothesis is S{0}".format(i+1),S) 
        if(len(temp)==0):
            print("For instance {0} the hypothesis is G{0}".format(i+1),G) 
        else:
            print("For instance {0} the hypothesis is G{0}".format(i+1),temp)

    if(a[i][num_attributes]=='No'):
       for j in range(0,num_attributes): 
           if(S[j]!=a[i][j] and S[j]!='?'):
              G[j]=S[j]
              temp.append(G)
              G=['?']*num_attributes
       print("For instance {0} the hypothesis is S{0}".format(i+1),S) 
       print("For instance {0} the hypothesis is G{0}".format(i+1),temp)
