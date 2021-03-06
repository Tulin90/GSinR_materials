### Comparing base R and dplyr functions

|Operation |Base R example | dplyr function | dplyr example  | 
|:---|:---|:---|:---|
| Pick columns | `gapminder[, c(1,3:4)]` | `select()` | `select(gapminder, country, year, lifeExp)`  |
| Pick rows | `gapminder[c(1,3,5), ]` | `slice()` | `slice(gapminder, c(1,3,5))` |
| Subset rows | `gapminder[gapminder$year == 2007, ]` OR `subset(gapminder, year == 2007)` | `filter()` | `filter(gapminder, year == 2007)`  | 
| Reorder rows | `gapminder[order(gapminder$lifeExp), ]`  | `arrange()` | `arrange(gapminder, lifeExp)`  |
| Add a column | `transform(gapminder, gdp = pop * gdpPercap)` | `mutate()` | `mutate(gapminder, gdp = pop * gdpPercap)` |
| Group data | - | `group_by()` | `gapminder %>% group_by(continent)` |
| Summarize data | `aggregate(lifeExp ~ continent, data = gapminder, FUN = mean)` | `group_by()` AND `summarize()` |  `gapminder %>% group_by(continent) %>% summarize(mean_lifeExp = mean(lifeExp))` |
