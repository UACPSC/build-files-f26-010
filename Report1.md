<!-- {% raw %} -->
# Makefile: build-files-f26-010

% git status

```console
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit (use -u to show untracked files)
```

Changed files:

```console
Makefile
```

Source: Implementation

```Make
# Build for srccomplexity

.PHONY:all
all : srccomplexity srcMLXPathCountTest

srccomplexity : srcComplexity.o srcMLXPathCount.o
	g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity

srcComplexity.o : srcComplexity.cpp srcMLXPathCount.hpp
	g++ -c srcComplexity.cpp

srcMLXPathCount.o : srcMLXPathCount.cpp srcMLXPathCount.hpp
	g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp

srcMLXPathCountTest : srcMLXPathCountTest.o srcMLXPathCount.o
	g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

srcMLXPathCountTest.o : srcMLXPathCountTest.cpp srcMLXPathCount.hpp
	g++ -c srcMLXPathCountTest.cpp

.PHONY:run
run : srccomplexity
	./srccomplexity srcMLXPathCount.cpp.xml

.PHONY:clean
clean :
	@rm -f srcComplexity.o srcMLXPathCount.o srcMLXPathCountTest.o srccomplexity srcMLXPathCountTest

```

## Comparison

Closest match: Section 010

% diff Makefile

```diff
```

% diff commit messages

```diff
```

## Steps

### Step 1: Add header comment to the Makefile ✓

Makefile ✓

Build ✓

```console
$ make
make: *** No targets.  Stop.
(exit status 2)

# files created:
```

### Step 2: Add srcComplexity.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcComplexity.o
g++ -c srcComplexity.cpp

# files created:
srcComplexity.o
```

### Step 3: Add srcMLXPathCount.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCount.o
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp

# files created:
srcMLXPathCount.o
```

### Step 4: Add executable srccomplexity to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srccomplexity
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
```

### Step 5: Add srcMLXPathCountTest.cpp to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCountTest.o
g++ -c srcMLXPathCountTest.cpp

# files created:
srcMLXPathCountTest.o
```

### Step 6: Add executable srcMLXPathCountTest to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make srcMLXPathCountTest
g++ -c srcMLXPathCountTest.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2

# files created:
a.out
srcMLXPathCount.o
srcMLXPathCountTest.o
```

### Step 7: Add all target to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make all
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
srcMLXPathCountTest
srcMLXPathCountTest.o
```

### Step 8: Add PHONY to target all ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
srcMLXPathCountTest
srcMLXPathCountTest.o
```

### Step 9: Add clean target ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest
$ make clean

# files created:
```

### Step 10: Add run target to the build ✓

Makefile ✓

Dependencies ✓

Build ✓

```console
$ make run
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
./srccomplexity srcMLXPathCount.cpp.xml
7

# files created:
srccomplexity
srcComplexity.o
srcMLXPathCount.o
```


## Make

% make

```console
g++ -c srcComplexity.cpp
g++ -I/usr/include/libxml2 -c srcMLXPathCount.cpp
g++ srcComplexity.o srcMLXPathCount.o -lxml2 -o srccomplexity
g++ -c srcMLXPathCountTest.cpp
g++ srcMLXPathCountTest.o srcMLXPathCount.o -lxml2 -o srcMLXPathCountTest
```

```console
total 92
-rw-rw-r-- 1 root root   819 Oct  6 13:00 Makefile
-rw-rw-r-- 1 root root   293 Oct  6 13:00 README.md
-rwxr-xr-x 1 root root 72616 Oct  7 15:46 srccomplexity
-rw-rw-r-- 1 root root   280 Oct  6 13:00 srcComplexity.1.md
-rw-rw-r-- 1 root root  1245 Oct  6 13:00 srcComplexity.cpp
-rw-r--r-- 1 root root  7064 Oct  7 15:46 srcComplexity.o
-rw-rw-r-- 1 root root  2086 Oct  6 13:00 srcMLXPathCount.cpp
-rw-rw-r-- 1 root root  8379 Oct  6 13:00 srcMLXPathCount.cpp.xml
-rw-rw-r-- 1 root root   664 Oct  6 13:00 srcMLXPathCount.hpp
-rw-r--r-- 1 root root  3528 Oct  7 15:46 srcMLXPathCount.o
-rwxr-xr-x 1 root root 71080 Oct  7 15:46 srcMLXPathCountTest
-rw-rw-r-- 1 root root   130 Oct  6 13:00 srcMLXPathCountTest.cpp
-rw-r--r-- 1 root root  1280 Oct  7 15:46 srcMLXPathCountTest.o
```

## Commit Messages

```console
05db799 Add run target to the build
29d35bb Add clean target
50210f1 Add PHONY to target all
1490226 Add all target to the build
62266b0 Add executable srcMLXPathCountTest to the build
7567562 Add srcMLXPathCountTest.cpp to the build
2f2764d Add executable srccomplexity to the build
4be1736 Add srcMLXPathCount.cpp to the build
d5468e1 Add srcComplexity.cpp to the build
b95ea24 Add header comment to the Makefile
7f01125 Initial commit
```


<!-- {% endraw %} -->
