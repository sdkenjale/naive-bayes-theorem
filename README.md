# naive-bayes-theorem
install.packages('e1071')
library(e1071)
data=read.csv("C:/Users/Vikrant/Downloads/diabetes.csv")
View(data)
head(data)
nbsmodel=naiveBayes(Outcome ~.,data=data)
nbsmodel
nbspred=predict(nbsmodel,data)
nbspred
tt=table(nbspred,data$Outcome)
tt
acc_test=sum(diag(tt)/sum(tt))
acc_test
