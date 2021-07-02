# hugo-site
Trying out hugo to build a static website using a hugo theme and publishing to github pages.

## Notes:
Ensure you have
1. Hugo installed
2. Git installed


## Steps:
```
1. Create a GitHub Repo with a README.md file
2. git pull the repo to your local machine.
3. Go to your repo in your local machine, then run the command
   hugo new site . --force

4. Create gh-pages in your local, and run the below commands  -
   echo "public" >> .gitignore
   git checkout --orphan gh-pages
   git reset --hard
   git commit --allow-empty -m "Initializing gh-pages branch"
   git push origin gh-pages
   git checkout master

 5. push the changes to main/master branch.
    Go to your git repo in GitHub UI and Click on Settings -->Pages and scroll down to "GitHub Pages" to get the git link
     and paste it to your front git repo page.

 6. Get a Hugo theme from https://themes.gohugo.io/, Click on to parsa-hugo theme, Go to "Download" which opens the git repo
    to the theme. Copy the Git CLI from the "Code" Section.

 7. In local machine,
    cd themes/
    git clone https://github.com/Naina-Gurung/hugo-site.git

 8. Copy all the folders and files from  parsa-hugo/exampleSite/* to the root/ directory.
    This will replace the config.toml file, content/ and static/ folders.

 9. Open the config.toml file in the root/ directory and replace the baseurl with  "https://naina-gurung.github.io/hugo-site/"
    so that the content gets directed to this git page link.

10.  Run the following commands to build and deploy the contents of public/ dir to the gh-pages branch.
     rm -rf public
     git worktree add -B gh-pages public origin/gh-pages
     hugo
     cd public && git add --all && git commit -m "publish site"
     git push origin gh-pages

```