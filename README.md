# R-programming

Let's break down the solutions for each of the questions using R code.

### 1. Find out all even numbers in the vector `x`.
```r
x <- c(3, 45, 67, 123, 44, 55, 67, 12, 11, 24, 56)
even_numbers <- x[x %% 2 == 0]
even_numbers
```

### 2. Extract the last two characters from the given vector `y`.
```r
y <- c('ab', 'sdzb', 'dzhji', 'iioqwe', 'kdcakk', 'qaw', 'pop')
last_two_chars <- substr(y, nchar(y) - 1, nchar(y))
last_two_chars
```

### 3. Create a sequence of odd numbers less than 100.
```r
odd_numbers <- seq(1, 99, by = 2)
odd_numbers
```

### 4. Find all the numbers divisible by 3 and 7 which are less than 100.
```r
divisible_by_3_and_7 <- (1:99)[(1:99) %% 3 == 0 & (1:99) %% 7 == 0]
divisible_by_3_and_7
```

### 5. Replace all the missing instances (`NA`) with the most repeated values in `z`.
```r
z <- c('ad', 'abd', NA, 'ad', 'abc', NA, 'ad', 'abc', 'abd', NA, 'ad')
most_repeated <- names(sort(table(z), decreasing = TRUE))[1]
z[is.na(z)] <- most_repeated
z
```

### 6. Replace all the missing values (`NA`) with mean and median in `x1`.
- Replacing with mean:
```r
x1 <- c(34, 56, 78, NA, 89, NA, 11, NA, 23, 45)
x1_mean <- ifelse(is.na(x1), mean(x1, na.rm = TRUE), x1)
x1_mean
```
- Replacing with median:
```r
x1_median <- ifelse(is.na(x1), median(x1, na.rm = TRUE), x1)
x1_median
```

### 7. Count all the words present in the vector `w`, excluding spaces.
```r
w <- c('  This is a string', 'This is also a string', 'Even this is a string  ', 'this is not')
word_count <- sum(sapply(strsplit(w, "\\s+"), function(x) length(x[x != ""])))
word_count
```

### 8. Extract the numbers and print the highest number from vector `n`.
```r
n <- c('3545abd', '677mm', '121ad2kaj', '78d45', '0sd0a1')
extracted_numbers <- as.numeric(gsub("\\D", "", n))
max_number <- max(extracted_numbers, na.rm = TRUE)
max_number
```
