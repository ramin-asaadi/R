## Socioeconomic development and life expectancy relationship
### Life Expectancy vs. GDP per Capita
- Does income affect health?

```{r}
library(tidyverse)
library(moderndive)
library(extrafont)
library(ggpubr)

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
