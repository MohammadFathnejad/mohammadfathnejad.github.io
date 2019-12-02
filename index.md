# Portfolio

---

## About. 
<p>
Hi there! I am a Computer Science Student at Goldsmiths University of london, computer enthusiast and a normal everyday friend with a passion to teach and facilitate learning for others. 

Born in Iran and raised in different locations around the world with non-identical cultures, I have some gained some understanding towards people in general. Compared to other places, I mostly lived in London, as it is also where I am studying for a bachelor’s degree in Computer Science. <br>

Though I was born in iran and Studied in Persian, I was always more pro-efficient in the English language as I am also half American and was always more comfortable speaking English rather than Farsi. However, because of the Persian Education method I am confident in Mathematics which boosted my apprehension in the C.S degree.

My passion for Teaching started when my university gave me an opportunity to facilitate learning for other students from either the same year as I was or a year below, which was called being a PAL (Peer Assisted Learning) Leader. 
</p>

---
## My Hobbies

**1.** Indoor Rock Climbing (AKA: Wall Climbing) <br>
Even though I am not that great at it but its a skill that I always wanted to acheive.<br>
**2.** Table Tinnis (AKA: Ping Pong)<br>
I have my own holding technique which I like to call the Devils Face. <br>
**3.** Vollyball <br>
**4.** Video Games <br>
They Say Old Habbits Never Die. <br>
**5.** Music Development (Using FruityLoops) <br>
A Recently started hobbie, still in development as I am still a rookie at it. Hoping to get better at it. <br>
**6.** PC Exploring ( Hardware and Software) <br>
 I like taking them apart and exploring the components and the built. As for Software, I like finding new things to download and comparing its usability. <br>



---
[My First Program...](http://example.com/)

**_Transportation problem, using northwest method, shadow cost and improvment indices._**
```pythonimport csv
#first we import the csv module so we could get access to our file.
#next we create all the necessary variables such as the empty lists for us to use later on.
ShadowListA= [-1, -1, -1]
ShadowListB= [-1, -1, -1]
ShadowListC= [-1, -1, -1]
ShadowListSupply= []
ShadowListDemand= []
ImprovementInA = [-1, -1, -1]
ImprovementInA_A = []
ImprovementInB = [-1, -1, -1]
ImprovementInB_B = []
ImprovementInC = [-1, -1, -1]
ImprovementInC_C = []
asdA = 0
asdB = 0
asdC = 0
Improved_indices_A = []
Improved_indices_B = []
Improved_indices_C = []
Alist = []
Blist = []
Clist = []
Demandlist = []
Supplylist = []
TotalPrises = []
#Next we will ask the user to input the name of the wanted File.
File_Lst = input("please write the name of the file(Without File Type): ")
#Next we will ask of What Type of file it is.
File_Type = input("please write the File Type(E.g: csv):  ")
File_Lst = File_Lst + "." + File_Type
#The combination of both inputs will result in such .e.g: "TextFile.csv".
#Next We Get all the numbers inside the text file and input them into a list. with each line being a sublist.
with open(File_Lst,) as x:
        File_Lst = list(list(Lst) for Lst in csv.reader(x))
print (File_Lst)
c = len(File_Lst)
#Next we make a Extraction function for each line being a list.
def Extraction(b, ListName, ASD):
    a = 0
    for t in range(c - ASD):
        for i in range (len(File_Lst[b])):
            (File_Lst[b][a]) = int(File_Lst[b][a])
        ListName.append(File_Lst[b][a])
        a +=1
    print (ListName)
#Next is the Extraction Procedure through calling the function.
Extraction(0, Alist, 0)
Extraction(1, Blist, 0)
Extraction(2, Clist, 0)
Extraction(3, Demandlist, 1)
Supplylist.append(Alist[-1])
Supplylist.append(Blist[-1])
Supplylist.append(Clist[-1])
print(Supplylist)
#Here we calculate the Total of Demands and the Total Supplies.
def Pricing(listNam, TxT):
    Total = 0
    PrC = 0
    for Pricing in range (len(listNam)):
        Total = listNam[PrC] + Total
        PrC +=1
    print (TxT, Total)
    return Total
TotalDemand = Pricing(Demandlist, "Total Demand: ")
TotalSupply = Pricing(Supplylist, "Total Supply: ")
# Now We Check if the table is Valid for solving using the North-west method.
if TotalDemand == TotalSupply:
    print (".Table Is Valid.")
# If the table was Valid we Continue the proccess.
# Next we print all the necessary tables for better user interface.
    print ("The Full Table is: ")
    print ("Row A is: ", Alist)
    print ("Row B is: ", Blist)
    print ("Row C is: ", Clist)
    print ("Demands : ", Demandlist)
    print ("supply: ", Supplylist)
#Next we create the intial table for as, -1, means empty cell.
    NewA = [-1, -1, -1]
    plyQ = Supplylist[0]
    print(plyQ)
    NewA.append(plyQ)
    NewB = [-1, -1, -1]
    plyW = Supplylist[1]
    print(plyW)
    NewB.append(plyW)
    NewC = [-1, -1, -1]
    plyE = Supplylist[2]
    print(plyE)
    NewC.append(plyE)
    print("intial table")
    print(NewA)
    print(NewB)
    print(NewC)
    print(Demandlist)
    print ("Now to Solve The Problem Using the North-West method: ")
#At the mean time while we are solving the table using north-west,
    #We are also calculating the Shadow Costs.
#We know the first shadow supply is always '0'.
#And the Shadow Demand is equivalent to the number in the first cell.    
    ShadowListSupply.append(0)
    ShadowListDemand.append(Alist[0])
    The_Difference = Supplylist[0] - Demandlist[0]
###As we know that doing The North-west method There are only 2 possible outcomes while solving.
    #Either the answer is smaller than 0 or larger. that is why we use the if statement for 'if' being one outcome,
        #And 'else' being the second outcome.
#Here we calculate each and every outcome for a 3 by 3 table, while calculating the Shadow Costs also.
    if The_Difference >= 0 :
        NewA[0] = Demandlist[0]
        NewA[1] = The_Difference
        ShadowListA[0] = Alist[0]
        ShadowListDemand.append(Alist[1] - ShadowListSupply[0])
        ImprovementInB[0] = Blist[0]
        ImprovementInC[0] = Clist[0]
        ImprovementInB_B.append(ImprovementInB[0])
        ImprovementInC_C.append(ImprovementInC[0])
        TotalPrises.append(NewA[0] * ShadowListA[0])
        ax = NewA[1] - Demandlist[1]
        if ax >= 0 :
            NewA[1] = Demandlist[1]
            NewA[2] = ax
            ShadowListA[1] = Alist[1]
            ImprovementInB[1] = Blist[1]
            ImprovementInC[1] = Clist[1]
            ImprovementInB_B.append(ImprovementInB[1])
            ImprovementInC_C.append(ImprovementInC[1])
            TotalPrises.append(NewA[1] * ShadowListA[1])
            ac = NewA[2] - Demandlist[2]
            if ac >= 0 :
                NewA[2] = Demandlist[2]
                ShadowListA[2] = Alist[2]
                ShadowListDemand.append(Alist[1] - ShadowListSupply[0])
                ShadowListDemand.append(Alist[2] - ShadowListSupply[0])
                ImprovementInB[2] = Blist[2]
                ImprovementInC[2] = Clist[2]
                ImprovementInB_B.append(ImprovementInB[2])
                ImprovementInC_C.append(ImprovementInC[2])
                TotalPrises.append(NewA[2] * ShadowListA[2])
            else:
                NewA[2] = ax
                a = Supplylist[1] + NewA[2]
                a = a - Demandlist[2]
                ShadowListA[2] = Alist[2]
                ShadowListSupply.append(Blist[1] - ShadowListDemand[1])
                ImprovementInC[2] = Clist[2]
                ImprovementInC_C.append(ImprovementInC[2])
                TotalPrises.append(NewA[2] * ShadowListA[2])
                if a >= 0 :
                    NewB[2] = Demandlist[2] - NewA[2]
                    ShadowListB[2] = Blist[2]
                    ShadowListDemand.append(Blist[2] - ShadowListSupply[0])
                    TotalPrises.append(NewB[2] * ShadowListB[2])
                else:
                    print("Something went VERY wrong here...")
        else:
            NewA[1] = The_Difference
            ab = Supplylist[1] + NewA[1]
            ab = ab - Demandlist[1]
            ShadowListA[1] = Alist[1]
            ImprovementInC[1] = Clist[1]
            ImprovementInA[2] = Alist[2]
            ImprovementInC_C.append(ImprovementInC[1])
            ImprovementInA_A.append(ImprovementInA[2])
            ShadowListSupply.append(Blist[1] - ShadowListDemand[1])
            TotalPrises.append(NewA[1] * ShadowListA[1])
            if ab >= 0 :
                NewB[1] = Demandlist[1] - NewA[1]
                NewB[2] = ab
                ShadowListB[1] = Blist[1]
                ShadowListDemand.append(Blist[2] - ShadowListSupply[1])
                av = NewB[2] - Demandlist[2]
                TotalPrises.append(NewB[1] * ShadowListB[1])
                if av >= 0 :
                    NewB[2] = Demandlist[2]
                    ShadowListB[2] = Blist[2]
                    ImprovementInC[2] = Clist[2]
                    ImprovementInC_C.append(ImprovementInC[2])
                    TotalPrises.append(NewB[2] * ShadowListB[2])
                else:
                    NewB[2] = Supplylist[2]
                    a = Supplylist[1] + NewB[2]
                    a = a - Demandlist[2]
                    ShadowListB[2] = Blist[2]
                    ShadowListSupply.append(Clist[2] - ShadowListDemand[2])
                    TotalPrises.append(NewB[2] * ShadowListB[2])
                    if a >= 0 :
                        NewC[2] = Demandlist[2] - NewB[2]
                        ShadowListC[2] = Clist[2]
                        TotalPrises.append(NewC[2] * ShadowListC[2])
                    else:
                        print("Something went VERY wrong here...")
            else:
                NewB[1] = Supplylist[1]
                a = Supplylist[2] + NewB[1] + NewA[1]
                a = a - Demandlist[1]
                ShadowListB[1] = Blist[1]
                ShadowListSupply.append(Clist[1] - ShadowListDemand[1])
                TotalPrises.append(NewB[1] * ShadowListB[1])
                if a >= 0 :
                    NewC[1] = Demandlist[1] - NewB[1] - NewA[1]
                    NewC[2] = a
                    ShadowListC[1] = Clist[1]
                    ShadowListC[2] = Clist[2]
                    ShadowListDemand.append(Clist[2] - ShadowListSupply[2])
                    TotalPrises.append(NewC[1] * ShadowListC[1])
                    TotalPrises.append(NewC[2] * ShadowListC[2])
                else:
                    print("Something went VERY wrong here...")
###
    else:
        NewA[0] = Supplylist[0]
        a = Supplylist[1] + NewA[0]
        a = a - Demandlist[0]
        ShadowListA[0] = Alist[0]
        ImprovementInA[1] = Alist[1]
        ImprovementInA[2] = Alist[2]
        ImprovementInA_A.append(ImprovementInA[1])
        ImprovementInA_A.append(ImprovementInA[2])
        TotalPrises.append(NewA[0] * ShadowListA[0])
        if a >= 0 :
            NewB[0] = Demandlist[0] - NewA[0]
            NEWB = Supplylist[1] - NewB[0]
            NewB[1] = NEWB
            ShadowListB[0] = Blist[0]
            ImprovementInC[0] = Clist[0]
            ImprovementInC_C.append(ImprovementInC[0])
            ShadowListSupply.append(Blist[0] - ShadowListDemand[0])
            TotalPrises.append(NewB[0] * ShadowListB[0])
            a = NewB[1] - Demandlist[1]
            if a >= 0 :
                NewB[1] = Demandlist[1]
                NewB[2] = a
                ShadowListB[1] = Blist[1]
                ImprovementInC[1] = Clist[1]
                ImprovementInC_C.append(ImprovementInC[1])
                ShadowListDemand.append(Blist[1] - ShadowListSupply[1])
                ShadowListDemand.append(Blist[2] - ShadowListSupply[1])
                TotalPrises.append(NewB[1] * ShadowListB[1])
                am = NewB[2] - Demandlist[2]
                if am >= 0 :
                    NewB[2] = Demandlist[2]
                    ShadowListB[2] = Blist[2]
                    ImprovementInC[2] = Clist[2]
                    ImprovementInC_C.append(ImprovementInC[2])
                    TotalPrises.append(NewB[2] * ShadowListB[2])
                else:
                    NewB[2] = a
                    an = Supplylist[2] + NewB[2]
                    an = an - Demandlist[0]
                    ShadowListB[2] = Blist[2]
                    TotalPrises.append(NewB[2] * ShadowListB[2])
                    if a >= 0 :
                        NewC[2] = Demandlist[2] - NewB[2]
                        ShadowListC[2] = Clist[2]
                        ShadowListSupply.append(Clist[2] - ShadowListDemand[2])
                        TotalPrises.append(NewC[2] * ShadowListC[2])
                    else:
                        print("Something went VERY wrong here...")
            else:
                NewB[1] = NEWB
                a = Supplylist[2] + NewB[1]
                a = a - Demandlist[1]
                ShadowListB[1] = Blist[1]
                ImprovementInB[2] = Blist[2]
                ImprovementInB_B.append(ImprovementInB[2])
                TotalPrises.append(NewB[1] * ShadowListB[1])
                if a >= 0 :
                    NewC[1] = Demandlist[1] - NewB[1]
                    NewC[2] = a
                    ShadowListC[1] = Clist[1]
                    ShadowListSupply.append(Clist[1] - ShadowListDemand[0])
                    TotalPrises.append(NewC[1] * ShadowListC[1])
                    if a >= 0 :
                        NewC[2] = Demandlist[2]
                        ShadowListC[2] = Clist[2]
                        ShadowListDemand.append(Clist[1] - ShadowListSupply[0])
                        ShadowListDemand.append(Clist[2] - ShadowListSupply[1])
                        TotalPrises.append(NewC[2] * ShadowListC[2])
                    else:
                        print("Something went VERY wrong here...")
                else:
                    print("The Supply and Demand Do not match.")
        else:
            NewB[0] = Supplylist[1]
            a = Supplylist[2] + NewB[0] + NewA[0]
            a = a - Demandlist[0]
            ShadowListB[0] = Blist[0]
            ImprovementInB[1] = Blist[1]
            ImprovementInB[2] = Blist[2]
            ImprovementInB_B.append(ImprovementInB[1])
            ImprovementInB_B.append(ImprovementInB[2])
            TotalPrises.append(NewB[0] * ShadowListB[0])
            if a >= 0 :
                NewC[0] = Demandlist[1] - (NewB[0] + NewA[0])
                NewC[1] = a
                NewC[2] = Supplylist[2] - a
                ShadowListC[0] = Clist[0]
                ShadowListC[1] = Clist[1]
                ShadowListC[2] = Clist[2]

                TotalPrises.append(NewC[0] * ShadowListC[0])
                TotalPrises.append(NewC[1] * ShadowListC[1])
                TotalPrises.append(NewC[2] * ShadowListC[2])
###############################################And finally, we Print all the answers we have gotten so far.
                #inclusing: North-west method, Shadow Costs and The Improvement indices.
    print(NewA)
    print(NewB)
    print(NewC)
    print(Demandlist)
    print("Now for Shadow Cost!!!")
    print(ShadowListA)
    print(ShadowListB)
    print(ShadowListC)
    print("Shadow Cost For Supply: ", ShadowListSupply)
    print("Shadow Cost For Demand: ", ShadowListDemand)
    print("~~Total Prise is: ", sum(TotalPrises))
    print()
    print("improvent indices in Row 1", ImprovementInA, ImprovementInA_A)
    print("improvent indices in Row 2", ImprovementInB, ImprovementInB_B)
    print("improvent indices in Row 3", ImprovementInC, ImprovementInC_C)
    print("the improved are: ")
    while asdA <= (len(ImprovementInA_A) - 1):
        Improved_indices_A.append(ImprovementInA_A[asdA] - ShadowListSupply[0] - ShadowListDemand[asdA + 1])
        asdA +=1
    while asdB <= (len(ImprovementInB_B) - 1):
        Improved_indices_B.append(ImprovementInB_B[asdB] - ShadowListSupply[1] - ShadowListDemand[asdB + 1])
        asdB +=1
    while asdC <= (len(ImprovementInC_C) - 1):
        Improved_indices_C.append(ImprovementInC_C[asdC] - ShadowListSupply[2] - ShadowListDemand[asdC])
        asdC +=1
    print(Improved_indices_A)
    print(Improved_indices_B)
    print(Improved_indices_C)
    Boolin = True
    Min_A = min(int(i) for i in Improved_indices_A)
    if Min_A >= 0:
        Min_B = min(int(i) for i in Improved_indices_A)
        if Min_B >= 0:
            Min_C = min(int(i) for i in Improved_indices_C)
            if Min_C >= 0:
                print ()
            else:
                Boolin = False
                print ("Third line is not Optimal.")
        else:
            Boolin = False
    else:
        Boolin = False
    if Boolin == True:
        print ("This table is optimal.")
        print ("~~~Stepping stone is Not needed.")
    if Boolin == False:
        print("This Table is Not optimal.")
    Minim = min(int(i) for i in Improved_indices_A and Improved_indices_C)
    if Minim in Improved_indices_A:
        print("The Minimum number is in Line A and is: ", Minim)
    if Minim in Improved_indices_B:
        print("The Minimum number is in Line B and is: ", Minim)
    if Minim in Improved_indices_C:
        print("The Minimum number is in Line C and is: ", Minim)       
#And of course if the total Supply is not Equal to the Total Demand, the table will not be valid for north-west.
else:
    print ("This Table Is Not Valid.")
print ("Thank you for using this Program. Press Enter key to End.")
Exiting = input("")


```
<img src=""/>

---

## Education and Employment.

- [Project 1 Title](http://example.com/)
- [Project 2 Title](http://example.com/)





---
## CV
[Click Here To View or Download My CV Via PDF.](/pdf/Mohammad_Fathnejad_CV.pdf)



---
