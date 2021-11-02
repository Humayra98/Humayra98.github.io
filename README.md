---
layout: default
---

# **Applying Etter’s Modern Technical Writing Principles to host an online resume and README**

## **Purpose**

This document has 2 goals:  

* Describe the practical steps of hosting and formatting a resume using the software stack: Markdown, a Markdown editor, GitHub Pages and Jekyll.  
* Relate the practical steps described above to the general principles or concepts of current technical writing, as explained in Andrew Etter’s book _Modern Technical Writing_.  

## **Prerequisites**

* A resume formatted in Markdown.
* A Markdown editor - Visual Studio Code. Other Markdown editors can also be used.
* A GitHub account.
* A distributed version control system - Git. It is recommended to install Git to work on project locally and then sync changes with the remote repository.
* A static site generator - Jekyll. It is recommended to install Jekyll to work on project locally.

## **Instructions**

### I. Create/edit a resume in Markdown  

  Use a Markdown editor like Visual Studio Code to create and edit the resume. Save it as index.md to make this content the home page of the static site.  

  ![Editing resume with Visual Studio Code](https://raw.githubusercontent.com/Humayra98/Humayra98.github.io/gh-pages/readme%20assets/resume%20md%20.png)

  As described in Etter’s book _Modern Technical Writing_, XML-based languages are a bad choice for online documentation. Content created in XML-based languages these languages are difficult to parse and editors are often costly or unavailable for specific systems. Whereas content created in lightweight markup languages like Markdown are easy to parse, easy to style, and there are plenty of free editors. Markdown is the most widely used lightweight markup language and so it is fast-evolving and gives a measure of future-proofing.

### II. Set up GitHub repository

  1. Click on “+” icon from top navigation bar.
  2. Select “New Repository”.
  3. Type in _username_.github.io as repository name, where _username_ is the GitHub username.
  4. Choose repository visibility – public or private.
  5. You may or may not choose to add a README file.
  6. Click create repository.  

      ![Create GitHub repository](https://raw.githubusercontent.com/Humayra98/Humayra98.github.io/gh-pages/readme%20assets/create%20repo.png)

  7. Click “Add file”.
  8. Upload the Markdown resume index.md.
  9. To work locally:  
      i. Go to the directory you want to save the project in.  
      ii. Run the following command from command line.  

          git clone https://github.com/username/username.github.io

  [final repo screenshot]  

  Nowadays, most developers use Distributed Version Control Systems (DVCS) like Git and Mercurial for software development. DVCS support offline work and are great for collaboration. In his book _Modern Technical Writing_, Etter strongly advised to store any documentation for a project in the same repository as the source code so that the documentation and code branches are always in sync. This also encourages developers to contribute to the repository since they don’t have to clone multiple repositories for code and documentation. DVCS’s popularity among developers is the main reason why technical writers use DVCS.

### III. Create a static site.

1. Choose a theme  
    From the GitHub repository, go to Settings -> Pages -> Choose theme  
        ![Choose theme from GitHub](https://raw.githubusercontent.com/Humayra98/Humayra98.github.io/gh-pages/readme%20assets/choose%20theme.png) 
    OR,  
    Add a configuration file _config.yml with the following line: remote_theme: username/repositoryname where repositoryname is the name of the repository for the chosen theme and username is the name of the owner of that repository.

2. Add front matter `layout: <name of the html file for the theme>` to the Markdown resume.

3. Customize theme  
    i. Copy the theme layout html from its original repository.  
    ii. add it to your project repository.
    iii. Modify html or add styling as necessary.

4. To test site locally,  
    i. Add the GitHub Pages gem to the Gemfile.  

        gem "github-pages", group: :jekyll_plugins  

    ii. Run `bundle install` to install gem-based themes.  
    iii. Run `bundle exec jekyll serve` to launch the site locally.  

  According to Etter, static websites are fast, simple, portable and secure. They don’t require any server-side application dependencies or databases. Static site generators like Jekyll make it easier to add complex styling or formatting to the site. Basically, a static site generator takes content written in lightweight markup language, templated HTML and CSS for theme, and then processes everything into a working website. The site can be easily modified by just updating the content and processing everything again.

### IV. Publish site on GitHub Pages

1. Make sure the remote repository is in sync with the local repository if files were modified locally.
2. From the GitHub Repository, go to Settings -> Pages.
3. Make sure the root is set to the source branch or publishing source.
4. To see published site, click on the url https://_username_.github.io/.

    ![Demo](https://raw.githubusercontent.com/Humayra98/Humayra98.github.io/gh-pages/readme%20assets/demo.gif)

### V. More Resources

  1. [Markdown tutorial](https://www.markdowntutorial.com/)
  2. [Etter, Andrew. Modern Technical Writing. Kindle edition, Self-published, 2016](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
  3. [Mike Dane's Jekyll Static Site Generator Tutorial](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)
  4. [Evan Will's GitHub Pages Tutorial](https://evanwill.github.io/go-go-ghpages-b/content/1-intro.html)

## **Authors and Acknowledgments**

Thanks to group-4 members for their invaluable feedback throughout the assignment.  

Theme template taken from GitHub repository [pages-themes/slate](https://github.com/pages-themes/slate). Thanks to the [theme template contributors](https://github.com/pages-themes/slate/graphs/contributors) for the theme template.

## **Frequently Asked Questions**

1. Why is Markdown better than a word processor?

    In the book _Modern Technical Writing_, Etter emphasized on keeping constantly changing documentation in version control. Simple word processors don’t allow that flexibility. Moreover, HTML export in word processors is very complicated and unsuitable for creating websites. On the other hand, it is very easy to maintain Markdown files with version control systems. Static site generators make it even easier to modify the content and add complexity to the site.

2. Why is my resume not showing up?

    There are 3 common reasons of why the resume might not show up,  
        i. The name of the Markdown file for resume is wrong. The name needs to be index.md for it to show up on the main page.  
        ii. The theme was customized but the theme layout filename was not included in the front matter of the markdown file.  
        iii. Sometimes, it can take up to 20 minutes for the site to publish after pushing changes to GitHub. If the changes cannot be seen in an hour, see [About Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/articles/about-jekyll-build-errors-for-github-pages-sites).
