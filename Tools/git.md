# Clear
* Clear all the ignore files: `git clean -fX`
* Force clean (include directory): `git clean -f -FXd`

# Submodule
* Add submodule
```
cd <folder>
git submodule add  <repo url>
```
* Get submodule after clone project
```
git submodule init
git submodule update
```

# Bisect
```
# stop means the commit with bug, while start means the commit with no bug
git bisect start <stop> <start>
# Decide the commit is good or bad until you find out the bad commit
git bisect good
git bisect bad
# Return origin commit
git bisect reset
```

# Patch
## Generate Patch
```
# Generate diff file without commit message
git diff <commit N> <commit N+3> --binary > <diff_name>
# Generate patch after commit ID
git format-patch <commit ID>
# Generate 3 patches before commit ID (included)
git format-patch -3 <commit>
# Generate 5 patches before HEAD (included), and put into patch_directory
git format-patch -5 -o <patch_directory>
# Get the patches from commit N to N+3 (not include N)
git format-patch <commit N>..<commit N+3>
```

## Apply patch
```
# Check conflict or not
git apply --check <patch_name>
# Apply patch without commit message
git apply <patch_name>
# Apply one patch
git am <patch_name>
# Apply all patches in patch_directory with order
git am <patch_directory>/*
```
