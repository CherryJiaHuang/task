#第一题
a<-c()
findNum<-function(y,l){
for(i in which(y==1))
if(all(i:(i+l-1) %in% which(y==1)))
  a<-c(a,i)
  a
}

#第二题
raw <- read.delim("data/weather.txt",check.names = F, na.strings = ".")
raw$element<-as.character(raw$element)
dif<-cbind(raw[raw$element=="tmax",][,c(1,2)],raw[raw$element=="tmax",][,4:34]-raw[raw$element=="tmin",][,4:34])

#第三题
library(hflights)
mean<-aggregate(hflights$ArrDelay,by=list(hflights$Year,hflights$Month,hflights$UniqueCarrier),FUN=quantile,probs=0.1,na.rm=T)
