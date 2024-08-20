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
PRACTICLE 

Here is the sequence of the code with comments to make it easier to understand:

### Comments in R
- Use `#` to comment out lines.
- No multi-line commenting, but you can comment multiple lines using `Ctrl + Shift + C`.

```r
# R is case sensitive
x
x = 5
x <- 5
x
X = "something"
X
```

### Naming Rules
```r
# Invalid: 1.more = 2.34
one.more = 2.34
onemoreobject = 2.34
one.more.object = 2.34

# Dots (.) and underscores (_) are allowed.
# Numbers are allowed but not at the beginning.
```

### Working with Environment
```r
ls()
x = "Hadley Wickham"
rm(one.more, one.more.object, onemoreobject)
ls()

# Remove all objects
rm(list = ls())
```

### Logical Values
```r
x = FALSE
x

x = TRUE
x

x = F
x
# FALSE is reserved; you cannot assign it a value:
FALSE = 20
x = TRUE
x = x + 0
```

### Class and Type of Objects
```r
x = "bunny"
y = F
z = 4.5
class(x)
class(y)
class(z)
typeof(x)
typeof(y)
typeof(z)
```

### Character and Numeric Operations
```r
v1 = "23.45"
class(v1)
v1 + 2  # Error: cannot perform numeric operations on characters

v2 = as.numeric(v1)
class(v2)
v2 + 2

x1 = 'one'
y = as.numeric(x1)  # Converts to NA since "one" isn't numeric
typeof(y)

v1 = "King"
class(v1)
v2 = as.numeric(v1)  # Returns NA because "King" isn't numeric
v2
class(v2)
```

### Function Documentation
```r
?sum
?smu  # Opens documentation (if available)
??smu  # Searches for the function if not found directly
```

### Numeric Operations
```r
x = 2
y = 8

x + y
x - y
x * y
x / y
x ^ y
x ** y

z = (x + y - (x / y)) ** (x / 10)
```

### Mathematical Functions
```r
tan(10)
log(2^14, 10)
log(2^14)
log(2^14, 2)
```

### String Operations
```r
x = "Sachin"
y = "Tendulkar"
z = "Cricket"

paste(x, y, z, sep = "+")
name = paste(x, y)
profile = paste(name, z, sep = ":")
profile

paste(x, y, z, sep = "$")
paste(x, y, z, sep = "%2")
paste0(x, y, z)
```

### String Replacement
```r
address = "1612-Lone Tower-Mumbai"
newAd = sub("-", "/", address)  # Replaces first occurrence of "-"
newAd1 = gsub('-', '/', address)  # Replaces all occurrences of "-"

nchar('dafdafad1344')
ip = "192.168.23.134:219"
abc = substr(ip, 1, 3)  # Extracts substring
abc

options(scipen = 999)  # Removes scientific notation penalty
```

### Logical Operations
```r
x = 7
y = 9

x > y
x < y
x == y
x != y
x >= y
x <= y

z = x > y
z

x = 20
x >= 1 & x <= 19

y = "SAchin"
y == "Sachin" | y == "SACHIN"
y == "SAchin" | y == "SACHIN"
```

### Vectors
```r
x = c(2, 4, 89, -10, 5, 6)  # Numeric vector
x
x = c(2, 3, 4, "a", FALSE)  # Character vector since one element is a character
x
class(x)

# Accessing elements
length(x)
x[3]
x[-3]
x[c(1, 3)]

p = c(1, 2, 5)
x[p]
x[c(1, 2, 5)]
x[-p]
x[c(3, 4, 2, 2, 10, 3)]

# Conditional access
x > 4
L = x > 4
x[L]
x[x > 4]

y = c("a", "a", "b", "c", "d", "b", "a")
x = c(34, 56, 12, -90, 34, 4, 8)
x[y == 'a']
y[x %% 3 == 0]
```

### Creating Sequences and Repeating Values
```r
x = 2:10
x
4:-1
-5:5
2.3:7.9

x = seq(1, 5, by = 0.3)
x

x = seq(5, 1, by = -0.3)
x

x = seq(1, 10, length = 21)
x

x = 1:5
y = seq(2, 3, length = 5)
z = c(x, y, 2, 3, 6)
length(z)

rep(2, 10)
rep("a", 5)
rep(c(1, 5, 6), 4)
rep(c("a", "b", "c", "b"), 4)
rep(c("a", "c", "b"), each = 4)
```

### Vector Operations
```r
x = 1:5
y = seq(3, 13, length = 9)
x + y
x * y
x - y
x / y

log(x)
2**x

paste0(1, "a")
x = 1:10
y = rep("a", 10)
paste0(x, y)

f = round(runif(10), 2)
paste(f, z, sep = "*", collapse = "+")
```

### Handling Vectors of Unequal Lengths
```r
x = 1:11
y = c(1, 2, 3)
x + y  # Warning: Length mismatch

x = c("a", "b")
y = 1:10
z = c("c", "d")
paste0(x, y, z)
```

### Special Utility Functions
```r
x = c("k", "j", "$", "1", "f")
y = letters
match(x, y)

x = c("k", "j", "$", "1", "F")
a = letters
b = LETTERS
c = c(a, b)
match(x, c)

x %in% y
100 %% 32
30 %% 12
30 %% 15

x = 56:78
which(x %% 5 == 0)
x = runif(40, 1, 100)
x[which(x %% 2 != 0)]

x = c(3, 4, 5, -10, 1, 2, 0)
sort(x)
y = c("art", "Ant", "Bat")
sort(y)

sort(x, decreasing = TRUE)
sort(y, decreasing = TRUE)
rev(y)
rev(x)

x = 1:100
sample(x, 3)
sample(x, 7)
sample(x, 7, replace = TRUE)
sample(c("a", "b", "c"), 10, replace = TRUE)

x = sample(c("a", "b", "c"), 1000, replace = TRUE, prob = c(0.6, .1, .3))
table(x)
unique(x)

is.na(c(1, 2, 3, NA, NA, 3, 4, 5))
x = c(1, 2, 3, NA, NA, 3, 4, 5)
sum(is.na(x))
sum(c(1, 2, 3, NA, NA, 3, 4, 5), na.rm = TRUE)
```

### Lists
```r
x = sample(1:100, 10)
y = sample(c("a", "b", "c"), 6, replace = TRUE)
z = 4.56

list1 = list(x, y, z)
list1[[2]][3]

list2 = list(a = x, b = y, c = z)
list2$b[3]
```

### Data Frames
```r
x = round(runif(30), 2)
y = sample(c("a", "b", "c"), 30, replace = TRUE)
d = data.frame(x, y)

names(d) = c("num", "char")
rownames(d) = paste0("R", 1:30)
dim(d)
nrow(d)
ncol(d)
str(d)

data(mtcars)
d1 = mtcars
d1[3, 6]
d1[3, ]
d1[, 6]

d1[c(3, 4,

 5), c(2, 6)]
d1[, c("hp", "drat")]
d1[3, c("hp", "drat")]

# Attach a data frame to simplify column access
attach(d1)
disp[3]
hp[7]
detach(d1)

d1$hp
str(d1)
summary(d1)
table(d1$cyl)
table(d1$cyl, d1$gear)
cylgear = table(d1$cyl, d1$gear)
```

### Importing Data
```r
data1 = read.table(file = "filename.csv", header = TRUE, sep = ",")
data1 = read.csv("filename.csv")
```

### Exporting Data
```r
write.csv(mtcars, "newfilename.csv")
```

This code guide provides you with various R functionalities ranging from simple operations to more advanced topics such as data manipulation with lists and data frames. If you need more detailed explanations or have any other questions, feel free to ask!
