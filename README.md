# udezereposit
install.packages('RPostgreSQL')
library(RPostgreSQL)
drv <- dbDriver('PostgreSQL')
con <- dbConnect(drv, dbname='aact',host='aact-db.ctti-clinicaltrials.org',port=5432,user=(username='chigomars'),password='Virtual321@')
aact_sample <- dbGetQuery(con,'select * from studies limit 38')
write.csv(aact_sample,file='aact_sample.csv')
print(aact_sample)
summary(aact_sample)

Query <- dbSendQuery(con,'select * from studies')
result <- dbFetch(Query, n=20)
results <- dbFetch(Query, n=1)
result
results
summary(results)

resultss <- dbFetch(Query, n=37)
resultss1 <- dbFetch(Query, n=1)
summary(resultss1)
