# Sales-recommendation-with-R

### Cargamos la base de datos
```
rm(list =ls())
data(mtcars)
view(mtcars)
```
### Parte 1: limpieza de datos

#1)
```
mtcars <- mtcars %>% mutate(kml = mtcars$mpg * (1.61/3.785))
mtcars %>%  arrange(kml)
```
#El auto con menor consumo es es el Toyota Carolla con 14,41 km/l

#2)
```
mtcars <- mtcars %>%  mutate(kg = mtcars$wt*1000/2.204)
mtcars %>% arrange(kg)
```
#El auto menos pesado es el Lotus Europa con 686.47 kg

#3)
```
mtcars <- mtcars %>% filter(cyl<=6)
view(mtcars)
```
#Se quitaron todos los autos con seis o más cilindros

#Parte 2: Análisis exploratorio de los datos

#1)
```
mtcars %>%  arrange(kml)
median(mtcars$kml)
quantile(mtcars$kml, seq(0,1,0.1))
```

#La mediana de consumo de gasolina es de 9.21

#2) 
```
mtcars <- mtcars %>%  mutate(Tipo_transmision= if_else(am==1, "Manual", "Automática"))
mtcars %>%  group_by(Tipo_transmision) %>%  summarize(mean(kml))
```
#Los autos automaticos son mejores que los manuales (si se los compara en relación al consumo de gasolina)

#3)
```
mtcars %>% arrange(kml)
mtcars <- mtcars %>% mutate(mediana_kml=median(kml), mediana_kg=median(kg))
mtcars <- mtcars %>%  mutate(consumo= if_else(mediana_kml>kml, "Alto", "Bajo"),peso= if_else(mediana_kg>kg, "Bajo", "Alto"))

table(mtcars$consumo, mtcars$Tipo_transmision)
```
#De los autos con transmisión automatica 2 son de consumo bajo y 5 de consumo alto
#De los autos con transmisión manual 4 son de consumo alto y 7 de consumo bajo

#Parte 3: Visualización de datos

#1)
```
ggplot(mtcars, aes(x=Tipo_transmision, y=kml, fill=Tipo_transmision)) + geom_boxplot() +
  stat_summary(fun= mean, geom= "point") +
  labs(title = "Estadísticos descriptivos del consumo", subtitle = "Por tipo de transmisión") +
  xlab("Tipo de transmisión") + ylab("Consumo") +
  scale_fill_discrete(name= "Tipo de transmisión", labels = c("Automática", "Manual"))
```
#2)
```
cor(mtcars$kml, mtcars$kg, method = "pearson")
```
#A medida que el peso disminuye el consumo se vuelve más eficiente (+Kilometros por litro).
#Graficamente
```
ggplot(mtcars, aes(x=kml, y=kg)) + geom_point() +
  labs(title = "Relación entre consumo y peso", subtitle = "Mediante un diagrama de dispersión") +
  xlab("Consumo") + ylab("Peso") 
```
