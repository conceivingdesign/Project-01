# Project-01
Generative and feseability building tool
This is a little part of a bigger algorithm which makes automatic buildings (Build-to-rent). 
My objective is to translate the Grasshopper Definition to python.
This is a good opportunity to meet, colaborate and learn with this community of developers.

import rhinoscriptsyntax as rs
import Grasshopper.DataTree as dt
import Grasshopper as gh

Key = Key
Values = Values
Values_To_Replace = Values_To_Replace
#------------------------------------
def listToTree(nestedList):
    dt = gh.DataTree[object]()
    for i,l in enumerate(nestedList):
        dt.AddRange(l,gh.Kernel.Data.GH_Path(i))
    return dt
#------------------------------------
Values_To_Replace = [list(i) for i in Values_To_Replace.Branches]
ValuesA = [list(i) for i in Values.Branches]
#------------------------------------
n_of_branches = Values.BranchCount
gh_to_py_MassAdition = []
for i in range(n_of_branches):
    gh_to_py_MassAdition.append(sum(Values.Branch(i)))
#------------------------------------
path_number_index = []
for i in range(n_of_branches):
    path_number_index.append(i)
#------------------------------------
c = zip(path_number_index, gh_to_py_MassAdition,Values_To_Replace)
#------------------------------------
def Sort(sub_li):
    sub_li.sort(key = lambda x: x[Key])
    return sub_li
yy = Sort(c)
a = listToTree(yy)
#------------------------------------
path_number = []
for item in yy:
   path_number.append(item[0])
b = path_number
#------------------------------------
bb = []
for item in yy:
   bb.append(item[2])
c = listToTree(bb)
#------------------------------------
#------------------------------------
MassAdition_Sorted = []
for item in yy:
   MassAdition_Sorted.append(item[1])
d = MassAdition_Sorted
#------------------------------------
longitudEjes = longitudEjes
coef_dominio = coef_dominio
#------------------------------------
valuesInside=[]
for i in longitudEjes:
    values1 = []
    for j in MassAdition_Sorted:
        if j > i:
            values1.append(j)
    valuesInside.append(values1)
e = listToTree(valuesInside)
#------------------------------------
list_length = []
for x in valuesInside:
    lista = []
    lista.append(len(x))
    list_length.append(lista)
a = list_length
print a
f = listToTree(a)
#------------------------------------
def list_length_series(xxx):
    b = []
    count = 0
    for x in xxx: 
        a =[]
        for posicion,x in enumerate(x):
            a.append(posicion)
        b.append(a)
    return b
count = list_length_series(valuesInside)
print count
g = listToTree(count)
#------------------------------------
