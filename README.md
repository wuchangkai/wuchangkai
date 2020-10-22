### Hi there 👋

<!--
**wuchangkai/wuchangkai** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
makeCacheMatrix <- function(x = matrix()) {
inverse <- NULL
set <- function(y) {
x <<- y
inverse <<- NULL
# use <<- to assign a value to an object in an environment
# different from the current environment.
}
get <- function() x
setinverse <- function(inverse) inverse <<- inverse
getinverse <- function() inverse
list(set = set, get = get,
setinverse = setinverse,
getinverse = getinverse)
}

cacheSolve <- function(x, ...) {
## @x: output of makeCacheMatrix()
## return: inverse of the original matrix input to makeCacheMatrix()

inverse <- x$getinverse()

# if the inverse has already been calculated
if (!is.null(inverse)){
    # get it from the cache and skips the computation. 
    message("getting cached data")
    return(inverse)
}

# otherwise, calculates the inverse 
data = x$get()
inverse <- solve(data, ...)

# sets the value of the inverse in the cache via the setinv function.
x$setinverse(inv)

return(inv)
}
