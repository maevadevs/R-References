# R Basics To Remember

## Foundations

- Modulo is `%%`
- Assignement is `<-`
- 3 Data Types: 
  - Numeric
  - Character
  - Logical
- Checking data types: `class(data)`

## Vector

- Create a vector: `my_vect <- c(1, 2, 3)`
- Range shortcut: `my_vect <- 1:9`
- Assign name to vector: `names(vector) <- c('name1', name2')`
- Sum of vector elements: `sum(vector)`

### Vector Selection

- `dest <- src[3]`
- `dest <- src[c("Tuesday", "Wednesday", "Thursday")]`
- `dest <- src[2:5]`

### Vector Filtering

- `dest <- src[src > 0]`

## Matrix

- Creation: `matrix(1:9, byrow=TRUE, nrow=3)`
- Assign row names: `rownames(my_matrix) <- row_names_vector`
- Assign columns names: `colnames(my_matrix) <- col_names_vector`
- Add row sum: `sum_vect <- rowSums(my_matrix)`
- Add column sum: `sum_vect <- colSums(my_matrix)`
- Row bind: `big_matrix <- rbind(matrix1, matrix2, vector1 ...)`
- Column bind: `big_matrix <- cbind(matrix1, matrix2, vector1 ...)`
- Real Matrix product: `%*%`

### Matrix Selection

- `my_matrix[row, col]`
- `my_matrix[1:3, 2:4]`
- `my_matrix[,1]`
- `my_matrix[1,]`

## Factors

- Nominal Categorical: `factor_vector <- factor(data_vector)`
- Ordinal Categorical: `factor_temp_vector <- factor(temp_vector, order = TRUE, levels = c("Low", "Medium", "High"))`
- Factor Levels: 

```r
# The order with which you assign the levels is important
# To correctly map "F" to "Female" and "M" to "Male", the levels should be set to c("Female", "Male"), in this order.
survey_vector <- c("M", "F", "F", "M", "M")
levels(factor_survey_vector) <- c("Female", "Male")
```

- Factor Summary: `summary(survey_vector)`

## Data Frame

- Quick looks:
  - `head(df)`
  - `tail(df)`
- Structure: `str(df)`
- Creation: `data.frame()`

```r
name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
type <- c("Terrestrial planet", "Terrestrial planet", "Terrestrial planet", "Terrestrial planet", "Gas giant", "Gas giant", "Gas giant", "Gas giant")
diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)
rotation <- c(58.64, -243.02, 1, 1.03, 0.41, 0.43, -0.72, 0.67)
rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)

planets_df <- data.frame(name, type, diameter, rotation, rings)
```

### Selection: `df[row, col]`

- `planets_df[1:3,2]`
- `planets_df[1:3,"type"]`
- `planets_df[,"type"]`
- `planets_df$type`
- `planets_df[planets_df['diameter'] > 2,]`
- `subset(planets_df, subset = diameter > 2)`

### Sorting

- `order(vect)`
- `planets_df[order(planets_df$diameter),]`

## Lists

- Same concept as Python list
- Creation: `my_list <- list(my_vector, my_matrix, my_df)`
- Named List: `my_list <- list(vec = my_vector, mat = my_matrix, df = my_df)`

```r
# Naming list after creation
my_list <- list(your_comp1, your_comp2)
names(my_list) <- c("name1", "name2")
```

- Accessing list element: `my_list[[1]]`
- Accessing list element by name: 

```r
my_list[["vec"]]
my_list$vec
```
