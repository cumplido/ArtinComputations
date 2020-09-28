##########################
##Computations on  A[D4]##
##########################

#PROCEDURE NonCyclicD4():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms from A[D4] to S6.
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds 
#to the image of si under the homomorphism.
#REMARK: We get 14400 homomorphisms in the list.

def NonCyclicD4():
    G=SymmetricGroup(6)
    L1=G.list()
    L2=[]
    for u1 in L1:
        for u3 in L1:
            if u1*u3*u1==u3*u1*u3 and u1<>u3: L2 = L2+[[u1,u3]]
    L3=[]
    for v in L2:
        u1=v[0]
        u3=v[1]
        for u2 in L1:
            if u1*u2==u2*u1 and u2*u3*u2==u3*u2*u3:L3=L3+[[u1,u2,u3]]
    L4=[]
    for v in L3:
        u1=v[0]
        u2=v[1]
        u3=v[2]
        for u4 in L1:
            if u1*u4==u4*u1 and u2*u4==u4*u2 and u3*u4*u3==u4*u3*u4:L4=L4+[[u1,u2,u3,u4]]
    L5=[]
    for v in L4:
        u0=L1[0]*L1[0]^(-1)
        u1=(v[3]*v[2]*v[1]*v[0])^3
        if u1==u0:L5=L5+[v]
    return L5

#PROCEDURE NonCyclicConjugationD4():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms from A[D4] to S6 up to conjugation.
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds 
#to the image of si under the homomorphism.
#REMARK: We get 40 homomorphisms.

def NonCyclicConjugationD4():
    G=SymmetricGroup(6)
    L1=G.list()
    L2=NonCyclicD4()
    def EstInclus(u,L):
        t=0
        for v in L:
            if u==v: t=t+1
        return t
    def ClasseConjugaison(v):
        L=[]
        for u in L1: L=L+[[u*v[0]*u^(-1),u*v[1]*u^(-1),u*v[2]*u^(-1),u*v[3]*u^(-1)]]
        return L
    def Simplification1(K1,K2):
        K3=[]
        for u in K1:
            if EstInclus(u,K2)==0: K3 = K3+[u]
        return K3
    K1=L2
    K2=[]
    while K1<>[]:
        u=K1[0]
        K2=K2+[u]
        K3=ClasseConjugaison(u)
        K1=Simplification1(K1,K3)
    return K2

#PROCEDURE NonCyclicConjugationD4_1():
#INPUT: None.
#OUPUT: List of non cyclic homomorphisms f from A[D4] to S6 up to 
#conjugation satisfying f(s1)<>f(s2), f(s1)<>f(s4) and f(s2)<>f(s4).
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds 
#to the image of si under the homomorphism.
#REMARK: We get 0 homomorphism.

def NonCyclicConjugationD4_1():
    L1=NonCyclicConjugationD4()
    L2=[]
    for v in L1:
        if v[0]<>v[1] and v[0]<>v[3] and v[1]<>v[3]: L2=L2 + [v]
    return L2

#PROCEDURE NonCyclicD4_2():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms f from A[D4] to S6 such that 
#f(s1)=f(s2).
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds  
#to the image of si under the homomorphism.
#REMARK: We get 8640 homomorphisms in the list.

def NonCyclicD4_2():
    L1=NonCyclicD4()
    L2=[]
    for v in L1:
        if v[0]==v[1]: L2 = L2+[v]
    return L2

#PROCEDURE NonCyclicConjugationD4_2():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms f from A[D4] to S6 such that 
#f(s1)=f(s2) up to conjugation.
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds  
#to the image of si under the homomorphism.
#REMARK: We get 24 homomorphisms in the list.

def NonCyclicConjugationD4_2():
    L1=NonCyclicConjugationD4()
    L2=[]
    for v in L1:
        if v[0]==v[1]: L2 = L2+[v]
    return L2

#PROCEDURE NonCyclicConjugationD4_3(L1):
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms f from A[D4] to S6 such that 
#f(s1)=f(s2) and f(s1.s3.s2.s1.s3.s1)<>1 up to conjugation.
#Each homomorphism is given by a 4-tuple (u1,u2,u3,u4), where ui corresponds  
#to the image of si under the homomorphism.
#REMARK: We get 0 homomorphism in the list.

def NonCyclicConjugationD4_3():
    G=SymmetricGroup(6)
    L1=G.list()
    u0=L1[0]*L1[0]^(-1)
    L2=NonCyclicConjugationD4_2()
    L3=[]
    for v in L2:
        y=v[0]*v[2]*v[0]*v[1]*v[2]*v[0]
        if y<>u0: L3=L3+[v]
    return L3

##########################
##Computations on  A[D6]##
##########################

#PROCEDURE ExceptionalCaseD6():
#INPUT: None.
#OUTPUT: List of elements in S8 that satisfy u1*v=v*u1, u2*v*u2=v*u2*v,  u3*v=v*u3, 
#u4*v=v*u4 and u5*v=v*u5, where u1=(1,2)(3,4)(5,6), u2=(2,3)(1,5)(4,6), u3=(1,3)(2,4)(5,6),
#u4=(1,2)(3,5)(4,6) and u5=(2,3)(1,4)(5,6) .
#REMARK: We get 1 element in the list, u1.

def ExceptionalCaseD6():
    G=SymmetricGroup(8)
    u1=G("(1,2)(3,4)(5,6)")
    u2=G("(2,3)(1,5)(4,6)")
    u3=G("(1,3)(2,4)(5,6)")
    u4=G("(1,2)(3,5)(4,6)")
    u5=G("(2,3)(1,4)(5,6)")
    L1=G.list()
    L2=[]
    for v in L1:
        if u1*v==v*u1 and u2*v*u2==v*u2*v and u3*v==v*u3 and u4*v==v*u4 and u5*v==v*u5:
            L2=L2+[v]
    return L2

##########################
##Computations on  A[E6]##
##########################

#PROCEDURE ExceptionalCaseE6():
#INPUT: None.
#OUTPUT: List of elements in S8 that satisfy u1*v=v*u1, u2*v*=v*u2,  u3*v*u3=v*u3*v, 
#u4*v=v*u4 and u5*v=v*u5, where u1=(1,2)(3,4)(5,6), u2=(2,3)(1,5)(4,6), u3=(1,3)(2,4)(5,6),
#u4=(1,2)(3,5)(4,6) and u5=(2,3)(1,4)(5,6) .
#REMARK: We get 0 element in the list.

def ExceptionalCaseE6():
    G=SymmetricGroup(8)
    u1=G("(1,2)(3,4)(5,6)")
    u2=G("(2,3)(1,5)(4,6)")
    u3=G("(1,3)(2,4)(5,6)")
    u4=G("(1,2)(3,5)(4,6)")
    u5=G("(2,3)(1,4)(5,6)")
    L1=G.list()
    L2=[]
    for v in L1:
        if u1*v==v*u1 and u2*v==v*u2 and u3*v*u3==v*u3*v and u4*v==v*u4 and u5*v==v*u5:
            L2=L2+[v]
    return L2

##########################
##Computations on  A[F4]##
##########################

#PROCEDURE ComputeSetE1ofF4():
#INPUT: None.
#OUTPUT: List of triples (u1,u2,u3) of elements of S6 such that u1*u2*u1 = 
#u2*u1*u2, u1*u3 = u3*u1, u2*u3 = u3*u2, u1 <> u2 and ord(u3) in {3, 6}.
#REMARK: We get 1440 elements in the list.

def ComputeSetE1ofF4():
    G=SymmetricGroup(6)
    L1=G.list()
    u0=G("()")
    L2=[]
    for u in L1:
        if u<>u0 and u^2<>u0 and u^6==u0: L2=L2+[u]
    L3=[]
    for u1 in L1:
        for u2 in L1:
            if u1*u2*u1==u2*u1*u2 and u1<>u2: L3=L3+[[u1,u2]]
    L4=[]
    for u in L3:
        for u3 in L2:
            if u[0]*u3==u3*u[0] and u[1]*u3==u3*u[1]: L4=L4+[[u[0],u[1],u3]]
    return L4

#PROCEDURE ComputeSetE10ofF4():
#INPUT: None.
#OUTPUT: List of triples (u1,u2,u3) of elements of S6 such that u1*u2*u1 =  u2*u1*u2, 
#u1*u3 = u3*u1, u2*u3 = u3*u2, u1 <> u2 and ord(u3) in {3, 6} up to conjugation.
#REMARK: We get the following 6 elements in the list:
#[(1,2), (2,3), (4,5,6)]
#[(1,2,3,4,5,6), (1,6,3,2,5,4), (1,3,5)(2,4,6)]
#[(1,2,3,4,5,6), (1,6,3,2,5,4), (1,5,3)(2,6,4)]
#[(1,4)(2,5)(3,6), (1,2)(3,4)(5,6), (1,3,5)(2,4,6)]
#[(2,3)(4,5,6), (1,2)(4,5,6), (4,5,6)]
#[(2,3)(4,5,6), (1,2)(4,5,6), (4,6,5)]

def ComputeSetE10ofF4():
    G=SymmetricGroup(6)
    L1=G.list()
    def Operation1(u,L):
        t=0
        for v in L:
            if u==v:t=t+1
        return t
    def Operation2(K1,K2):
        K3=[]
        for u in K1:
            if Operation1(u,K2)==0: K3=K3+[u]
        return K3
    def Operation3(u):
        K1=[]
        for v in L1: K1=K1+[[v*u[0]*v^(-1),v*u[1]*v^(-1),v*u[2]*v^(-1)]]
        return K1
    L2=[]
    L3=ComputeSetE1ofF4()
    while L3<>[]:
        u=L3[0]
        L2=L2+[u]
        L4=Operation3(u)
        L3=Operation2(L3,L4)
    return L2  

#PROCEDURE ComputeSetE10ofF4_1():
#INPUT: None.
#OUTPUT: List of triples (u1,u2,u3) of elements of S6 such that u1*u2*u1 =  
#u2*u1*u2, u1*u3 = u3*u1, u2*u3 = u3*u2, u1 <> u2 and ord(u3) in {3, 6}, up 
#to conjugation, and such that (u1*u2*u3^2)^3=1.
#REMARK: We get 6 elements in the list.

def ComputeSetE10ofF4_1():
    L1=[]
    L2=ComputeSetE10ofF4()
    for u in L2:
        v=(u[0]*u[1]*u[2]^2)^3
        if v*v==v: L1=L1+[u]
    return L1 

#PROCEDURE ComputeSetE2ofF4():
#INPUT: None.
#OUTPUT: List of quadruples (u1,u2,u3,u4) of elements of S6 such that 
#u1*u2*u1 = u2*u1*u2, u1*u3 = u3*u1, u1*u4 = u4*u1, u2*u3*u2*u3 = 
#u3*u2*u3*u2, u2*u4 = u4*u2, u3*u4*u3 = u4*u3*u4, u1 <> u2 and u3 <> u4.
#REMARK:  We get 1440 elements in the list.

def ComputeSetE2ofF4():
    G=SymmetricGroup(6)
    L1=G.list()
    L2=[]
    for u1 in L1:
        for u2 in L1:
            if u1*u2*u1==u2*u1*u2 and u1<>u2: L2=L2+[[u1,u2]]
    L3=[]
    for v1 in L2:
        for v2 in L2:
            if v1[0]*v2[0]==v2[0]*v1[0] and v1[0]*v2[1]==v2[1]*v1[0] and v1[1]*v2[0]*v1[1]*v2[0]==v2[0]*v1[1]*v2[0]*v1[1] and v1[1]*v2[1]==v2[1]*v1[1]: L3=L3+[[v1[0],v1[1],v2[0],v2[1]]]
    return L3

#PROCEDURE ComputeSetE20ofF4():
#INPUT: None.
#OUTPUT: LIST of quadruples (u1,u2,u3,u4) of elements of S6 such that 
#u1*u2*u1 = u2*u1*u2, u1*u3 = u3*u1, u1*u4 = u4*u1, u2*u3*u2*u3 = 
#u3*u2*u3*u2, u2*u4 = u4*u2, u3*u4*u3 = u4*u3*u4, u1 <>u2 and u3 <> u4 
#up to conjugation.
#REMARK: We get the following 2 elements in the list:
#[(1,2), (2,3), (5,6), (4,5)],
#[(1,4)(2,5)(3,6), (1,2)(3,4)(5,6), (1,4)(2,3)(5,6), (1,6)(2,5)(3,4)]

def ComputeSetE20ofF4():
    G=SymmetricGroup(6)
    L1=G.list()
    def Operation1(u,K):
        t=0
        for v in K:
            if u==v:t=t+1
        return t
    def Operation2(K1,K2):
        K3=[]
        for u in K1:
            if Operation1(u,K2)==0: K3=K3+[u]
        return K3
    def Operation3(u):
        K1=[]
        for v in L1: K1 = K1+[[v*u[0]*v^(-1),v*u[1]*v^(-1),v*u[2]*v^(-1),v*u[3]*v^(-1)]]
        return K1
    L2=[]
    L3=ComputeSetE2ofF4()
    while L3<>[]:
        u=L3[0]
        L2=L2+[u]
        L4=Operation3(u)
        L3=Operation2(L3,L4)
    return L2

#PROCEDURE ComputeSetE20ofF4_1():
#INPUT: None.
#OUTPUT: LIST of quadruples (u1,u2,u3,u4) of elements of S6 such that 
#u1*u2*u1 = u2*u1*u2, u1*u3 = u3*u1, u1*u4 = u4*u1, u2*u3*u2*u3 = 
#u3*u2*u3*u2, u2*u4 = u4*u2, u3*u4*u3 = u4*u3*u4, u1 <>u2 and u3 <> u4 
#up to conjugation, and such that (u1*u2*u3*u4)^3=1.
#REMARK: We get 2 elements in the list.

def ComputeSetE20ofF4_1():
    L1=[]
    L2=ComputeSetE20ofF4()
    for u in L2:
        v=(u[0]*u[1]*u[2]*u[3])^3
        if v*v==v: L1=L1+[u]
    return L1

##########################
##Computations on  A[H4]##
##########################

#PROCEDURE HomomorphismsH4():
#INPUT: None.
#OUTPUT: List of homomorphisms f from A[H4] to S6. Each homomorphism is 
#given by a 4-tuple (u1,u2,u3,u4), where ui corresponds to the image of si 
#under the homomorphism.
#REMARK: We get 720 homomorphisms in the list.

def HomomorphismsH4():
    G=SymmetricGroup(6)
    L1=G.list()
    L2 = []
    for u1 in L1:
        for u2 in L1:
            if u1*u2*u1*u2*u1==u2*u1*u2*u1*u2: L2=L2+[[u1,u2]]
    L3=[]
    for v in L2:
        for u in L1:
            if v[0]*u==u*v[0] and v[1]*u*v[1]==u*v[1]*u: L3=L3+[[v[0],v[1],u]]
    L4=[]
    for v in L3:
        for u in L1:
            if v[0]*u==u*v[0] and v[1]*u==u*v[1] and v[2]*u*v[2]==u*v[2]*u: L4=L4+[[v[0],v[1],v[2],u]]
    L5=[]
    for v in L4:
        if (v[0]*v[1]*v[2]*v[3])^(15)==L1[0]: L5=L5+[v]
    return L5

#PROCEDURE HomomorphismsH4_1():
#INPUT: None.
#OUTPUT: List of cyclic homomorphisms f from A[H4] to S6.
#REMARK: We get 720 homomorphisms in the list.

def HomomorphismsH4_1():
    L1=HomomorphismsH4()
    L2=[]
    for v in L1:
        if v[0]==v[1] and v[0]==v[2] and v[0]==v[3]: L2=L2+[v]
    return L2

##########################
##Computations on  A[H3]##
##########################

#PROCEDURE SubgroupS5():
#INPUT: None.
#OUTPUT: The order of the subgroup of S5 generated by u1 = (2,4)(3,5), u2 
#= (1,2)(4,5), u3 = (2,3)(4,5).
#REMARK: The order is 60.

def SubgroupS5():
    G=SymmetricGroup(5)
    u1=G("(2,4)(3,5)")
    u2=G("(1,2)(4,5)")
    u3=G("(2,3)(4,5)")
    H = G.subgroup([u1,u2,u3])
    return H.order()

#PROCEDURE NonCyclicH3():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms from A[H3] to S5. Each 
#homomorphism is given by a 3-tuple (u1,u2,u3), where ui corresponds to the 
#image of si under the homomorphism.
#REMARK: We get 240 homomorphisms in the list.

def NonCyclicH3():
    G=SymmetricGroup(5)
    L1=G.list()
    L2=[]
    for u1 in L1:
        for u2 in L1:
            if u1*u2*u1*u2*u1==u2*u1*u2*u1*u2 and u1<>u2: L2 = L2+[[u1,u2]]
    L3=[]
    for v in L2:
        for u3 in L1:
            if v[0]*u3==u3*v[0] and v[1]*u3*v[1]==u3*v[1]*u3:L3=L3+[[v[0],v[1],u3]]
    return L3

#PROCEDURE NonCyclicConjugationH3():
#INPUT: None.
#OUTPUT: List of non cyclic homomorphisms from A[H3] to S5, up to 
#conjugation. Each homomorphism is given by a 3-tuple (u1,u2,u3), where ui 
#corresponds to the image of si under the homomorphism.
#REMARK: We get the following 2 elements in the list:
#[(1,2,3,4,5), (1,4,2,3,5), (1,5,4,3,2)]
#[(2,4)(3,5), (1,2)(4,5), (2,3)(4,5)]

def NonCyclicConjugationH3():
    G=SymmetricGroup(5)
    L1=G.list()
    def EstInclus(u,L):
        t=0
        for v in L:
            if u==v: t=t+1
        return t
    def ClasseConjugaison(v):
        K1=[]
        for u in L1: K1=K1+[[u*v[0]*u^(-1),u*v[1]*u^(-1),u*v[2]*u^(-1)]]
        return K1
    def Simplification1(K1,K2):
        K3=[]
        for u in K1:
            if EstInclus(u,K2)==0: K3 = K3+[u]
        return K3
    L2=NonCyclicH3()
    L3=[]
    while L2<>[]:
        u=L2[0]
        L3=L3+[u]
        L4=ClasseConjugaison(u)
        L2=Simplification1(L2,L4)
    return L3













