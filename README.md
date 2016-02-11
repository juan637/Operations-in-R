# Operations-in-R
 first week
 
 ##Factors
x<-factor(c("yes","yes","no", "yes", "no"))
x
table(x)
unclass(x)
attributes("levels")

##factors
x<-factor(c("yes","yes","no", "yes", "no"))
levels=(c("not","yes"))
x

x<-c(1,2,NA,10,3)
is.na(x)

##data frames
x<-data.frame(foo=1:4, bar=c(T,T,F,F))
x
nrow(x)
ncol(x)

##names attributes
x<-1:3
names(x)
names (x)<-c("foo","bar","norf")
x
names(x)

x<-list(a=1,b=2,c=3)
x

m<-matrix(1:4,nrow=2,ncol=2)
m
dimnames(m)<-list(c("a","b"),c("c","d"))
m

##dput-ting R objects
y<-data.frame(a=1,b="a")
dput(y)
dput(y,file="y.R")
new.y<-dget("y.R")
new.y

##subsetting
x<-c("a","b","c","c","d","a")
x[1]
x[2]
x[3:4]
x[1:5]
x[x>"a"]
x[x>"b"]
x[x>"d"]
x[x<"d"]

##subsetting a logical vector
u<-x>"a"
u 
x[u]

##subsetting lists
x<-list(foo=1:4,bar=0.6)
x[1]
x$foo

x[[1]]
x$bar
x[1]

##subsetting lists-multiple elements of a list 
x<-list(foo=1:4, bar=0.6, baz="hello")
x[c(1,3)]

##subsetting lists-2*[] 
x<-list(foo=1:4, bar=0.6, baz="hello")
name<-"foo"
x[[name]]
x$name
x$foo

##subsetting lists-2*[]-take an integer sequence
x<-list(a=list(10,12,14), b=c(3.14, 2.81))
x[[c(1,3)]]
x[[1]][[3]]

x[c(2,1)]

##subsetting Matrices
x<-matrix(1:6,2,3)
x[1,2]
print(matrix)
x
x[1,3]
x[2,3]

##subsetting Matrices-extracting single elements
x<-matrix(1:6,2,3)
x[1,2]
x[1,2,drop=FALSE]

##subsetting Matrices-extracting single column or rows
x<-matrix(1:6,2,3)
x[1, ]
x[1, ,drop=FALSE]
x[ ,1]
x[ ,1,drop=FALSE]

##subsetting with names
x<-list(sardvark=1:5)
x$s
x[["s"]]
x[["s",exact=FALSE]]

##subsetting=removing NA Values
x<-c(1,2,NA,4,NA,5)
other<-is.na(x)
x[!other]
other

x<-c(1,2,NA,4,NA,5)
y<-c("NA","b","NA","d","NA","f")
nice<-complete.cases(x,y)
nice
x[nice]
y[nice]
x
y

##Vectorized operations
x<-1:4
y<-6:9
x+y
x>2
x>=2
y==8

##vectorized operations-matrices
x<-matrix(1:4,2,2)
y<-matrix(rep(10,4),2,2)
y
x*y
x/y
x%*%y

##Quiz 1
x<-4
class(x)
x<-c(4,"a",TRUE)
class(x)
x<-c(1,3,5)
y<-c(3,2,10)
cbind(x,y)
x<-list(2,"a","b",TRUE)
x[[2]]
x<-1:4
y<-2
x+y
x<-c(3,5,1,10,12,6)
x[x<6]=0
print(x[x<6]=0)

hw1_data
x<-hw1_data
x[ ,2]
x[2, ]
x[3, ]
x[1:2, ]


#Loop
x<-c("a","b","c","d")
for(i in 1:4){print(x[i])}
for(i in seq_along(x)){print(x[i])}
for(letter in x){print(letter)}
count<-0
while(count< 10){print(count)count<-count+1}

z<-5
while(z>=3&&z<=10){print(z)} 
coin<-rbinom(1,1,0.5) 
if (coin==1{##random walk
  z<z+1} else{
    z<-z-1}})

x0<-1
tol<-1e-8
repeat{x1<-computeEstumate() if(abs(x1-x0)<tol){break}else{x0<-x1}}
