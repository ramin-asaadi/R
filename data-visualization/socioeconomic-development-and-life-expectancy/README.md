## Socioeconomic development and life expectancy relationship
### Life Expectancy vs. GDP per Capita

```{r}

library(tidyverse)
library(moderndive)
library(extrafont)
library(ggpubr)

(1) GDP per capita on Five Continents

gapminder %>% 
  ggplot(mapping = aes(x = year, y = gdpPercap)) +
  geom_line(color="orange", aes(group = country)) +
  geom_smooth(size = 1.1, method = "loess", se = FALSE) +
  scale_y_log10(labels=scales::dollar) +
  facet_wrap(~ continent, ncol = 5) +
  labs(x = "Year",
       y = "GDP per capita",
       title = "GDP per capita on Five Continents") +
  theme(legend.position = "none") +
  theme(text = element_text(size = 14, family = "Futura")) +
  theme_cleveland()

```

```{r}

(2) Life Expectancy on Five Continents

gapminder %>% 
  ggplot(mapping = aes(x = year, y = lifeExp)) +
  geom_line(color="orange", aes(group = country)) +
  geom_smooth(size = 1.1, method = "loess", se = FALSE) +
  scale_y_log10(labels=scales::dollar) +
  facet_wrap(~ continent, ncol = 5) +
  labs(x = "Year",
       y = "Life Expectacy") +
  theme_pubclean()


```



  
```{r}

(3) Does income affect health?

gapminder %>%
  ggplot(aes(gdpPercap, lifeExp)) +
  geom_point(color = "orange") +
  scale_x_log10(labels = scales::dollar) +
  geom_smooth(method = "loess") +
  labs(x = "GDP Per Capita", y = "Life Expectancy in Years",
       title = "Economic Growth and Life Expectancy",
       subtitle = "Data points are country-years",
       caption = "Source: Gapminder") +
  facet_wrap(~ continent, nrow = 1) +
  theme(text = element_text(size = 14, family = "Futura")) +
  theme_cleveland()

```

![gdpPerCapita_lifeExpectancy](https://github.com/ramin-asaadi/R/assets/155740766/ce90892e-61ff-44fa-98b8-1019baed5fc3)