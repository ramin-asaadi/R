### Motor Trend Car Road Tests

Description: The data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973–74 models). Data frame includes 32 observations on 11 (numeric) variables.

- mpg	Miles/(US) gallon
- cyl	Number of cylinders
-	disp	Displacement (cu.in.)
-	hp	Gross horsepower
-	drat	Rear axle ratio
-	wt	Weight (1000 lbs)
-	qsec	1/4 mile time
-	vs	Engine (0 = V-shaped, 1 = straight)
-	am	Transmission (0 = automatic, 1 = manual)
-	gear	Number of forward gears
-	carb	Number of carburetors

```{r}
library(ggcorrplot)
library(corrplot)

corr = round(cor(mtcars), 1)

# plot

corrplot(corr, method = "pie")

```
### Correlogram of mtcars

![Rplot03](https://github.com/ramin-asaadi/R/assets/155740766/71556639-01ed-4d41-8c73-98c607ca7010)



