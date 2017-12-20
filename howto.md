# _Steven_ and _Greg_ deserve loads of praise for their patience and teaching skill
## Here's what I've learned so far:

1. How to **write** Markdown content in **Atom**
2. How to **convert** Markdown to html using **Pandoc**
3. How to **save** that content in **Github** (so [TechRandy](techrandy.html) can make pull requests); and
4. How to **deploy** that content to the internet using **cloud.gov** and **github pages**

## Getting Started

* First, from the command line you can find your last login by typing:

  ```
  cf login --sso
  ```

* then push up arrow key

* Next, get and enter a one-time authorization code to login into cloud.gov

* Find your current directory by typing:

  ```
  ls
  ```

* You can checkout all the apps you have in cloud.gov by typing:

  ```
  cf apps
  ```

* to delete an app from cloud.gov type:

  ```
  cf delete [app name] -r
  ```

* to work on an Atom file you have to be in the right directory (hint...check the **dev** file for examples) type:

  ```
  cd [name of atom file]
  ```

  * in case you forget **git** or **cf** commands and want a reminder, type:

  ```
  git [tab] or cf [tab]
  ```

**PRO TIP:** to avoid typos, just type the first few letters of your file and then hit *tab* and it fills in the rest of the word!

## Creating content in Atom
  **PRO TIP:** to access Atom emojis type control/command/space and 💥  they appear

* create a new .md file (tool bar upper left) or add to an existing file (for example index.md) and add new content using Markdown

* to include this new content as a link on an existing website, then add a link in the original website .md file (for example index.md)

* create a new .html file (for example index.html)

* use Pandoc to **_magically_** convert the .md file to html by typing:

  ```
  pandoc [file name.md] -o [file name.html] -s
  ```

* to preview the website before saving it to GitHub or deploying it to Cloud.gov

  ```
  open [file name].html
  ```

* remember if you're adding new content to an existing website with a link, you need to add the link to the original .md file and update the original .html file (using same pandoc process) to include an the html link to the new content

## Saving to Github
- **Remember your GitHub repo needs to include the following files:**

  1. index.md;

  2. index.html;
      * (note "index.html" file name is important for pushing to cloud.gov but doesn't really matter for GitHub)

  3. manifest.yml

      * (which can be copied and reused from another repo if you're pushing content to an existing website, if it's going to a different website then it'll need a new name in the .yml file)

- to see what files you've got in GitHub already type:

  ```
  git status
  ```

  ```
  git pull
  ```

* to save all your updated Atom files to GitHub type:

  ```
  git add .
  ```

* commit and push those changes to GitHub by typing:

  ```
  git commit -m "[include a description of the change]"
  ```

  ```
  git push
  ```

## Pushing content into the ether from Atom to Cloud.gov

* Just type:

  ```
  cf push
  ```

## Pushing content from GitHub Pages to local machine and then to Cloud.gov

* Make and Commit changes in GitHub then pull those into local machine by typing;

```
git pull
```

* Remember to update the .html file for whatever you've made changes to by typing:

```
pandoc [file name.md] -o [file name.html] -s
  ```

* Then push that to Cloud.gov by typing:

  ```
  cf push
  ```

## And voilá it's there for all the world to see...

👋  🌎
