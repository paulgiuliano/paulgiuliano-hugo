#!/bin/bash

echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

echo -e "\033[0;32mBuilding and committing Public...\033[0m"
# Build the project.
hugo # if using a theme, replace by `hugo -t <yourtheme>`

#Copy CNAME file to public folder
cp CNAME public/
# Go To Public folder
cd public

# Add changes to public
git add -A

# Commit changes to public
msg="rebuilding site `date`"
if [ $# -eq 1 ]
  then msg="$1"
fi
git commit -m "$msg"

# Push source and build repos in public
git push origin master

# Come Back to master
cd ..

echo -e "\033[0;32mCommitting and pushing Master...\033[0m"
# Add changes to master
git add -A

# Commit changes to master
msg="Deployed site `date`"
if [ $# -eq 1 ]
  then msg="$1"
fi
git commit -m "$msg"

# Push source and build master
git push origin master

echo -e "\033[0;32mDone!\033[0m"
