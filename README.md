# Series-de-Tiempo
temporal<-tempfile()
download.file("http://www.beta.inegi.org.mx/contenidos/proyectos/enchogares
/regulares/enoe/microdatos/enoe_15ymas/2016/2016trim1_dbf.zip",temporal)
files=unzip(temporal, list=TRUE)$Name
unzip(temporal, files=files[grepl("dbf", files)])
install.packages("foreign")
require(foreign)
SDEMT116<-data.frame(read.dbf("sdemt116.dbf"))
View(SDEMT116)

nombres<- c ("sergio", "carlos", "paula")
edad <- c(23,43,51)
base1 <- data.frame (nombres,edad)

3+4
3+5

table(SDEMT116$SEX) ##BUSCA CUANTOS HAY DE CADA SEXO
table(SDEMT116$ENT)
install.packages("questionr") ##bajamos de internet
require(questionr) ##mandamos a llamar la libreria a mi sesion de R
wtd.table (SDEMT116$SEX, weights = SDEMT116$FAC)
