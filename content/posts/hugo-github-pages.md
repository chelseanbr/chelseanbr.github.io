---
title: "Creating a Website with Hugo & Github Pages"
date: 2023-07-29T14:22:54-07:00
draft: False
# description: "A blog post"
# image: "/images/hugo-github-pages/building_website.jpeg"
type: "post"
tags: ["blog", "code"]
showTableOfContents: true
---
![/images/hugo-github-pages/building_website.jpeg](/images/hugo-github-pages/building_website.jpeg)

## What is Hugo?

Hugo (https://gohugo.io) is a popular open-source framework that makes it super fast to build and publish static websites like this one. It is written in Go, easy to install, and there are hundreds of cool themes to choose from!

## What About GitHub Pages?

In order to make your website publicly available, you'll need to host it somehow. GitHub Pages (https://pages.github.com) allows you to host static websites straight from GitHub repositories for FREE!

## Prerequisites

First, you will need:
1. An account at https://github.com
2. A text editor like VSCode (https://code.visualstudio.com)
3. Familiarity with the command line
4. Hugo (https://gohugo.io/installation/)
5. Git (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Creating Your Site

1. In GitHub, create a new public repository exactly named `<YOUR_USERNAME>.github.io` where `<YOUR_USERNAME>` is your GitHub username.
    - For example, mine is `chelseanbr.github.io`
2. On the command line, `cd` to where you want to store your website project, then `git clone` your newly created repository
3. Then run the following commands to create your Hugo website:
    ```bash
    hugo new site <YOUR_USERNAME>.github.io
    cd <YOUR_USERNAME>.github.io
    ```
    - You will see newly created folders and files:
        ```bash
        ❯ tree
        .
        ├── archetypes
        │   └── default.md
        ├── assets
        ├── content
        ├── data
        ├── hugo.toml
        ├── layouts
        ├── static
        └── themes

        8 directories, 2 files
        ```
4. Choose a theme to use for your website at: https://themes.gohugo.io
 - For your desired theme, click Download to go to the theme's GitHub repo and copy its HTTPS clone url, as shown below with the Gokarna theme (https://themes.gohugo.io/themes/gokarna/):

    ![gokarna_theme_download.png](/images/hugo-github-pages/gokarna_theme_download.png)
    ![gokarna_theme_clone.png](/images/hugo-github-pages/gokarna_theme_clone.png)

5. Now you can add the theme to your website, here is an example with the Gokarna theme:
    ```bash
    # You should still be in your <YOUR_USERNAME>.github.io directory
    git submodule add https://github.com/526avijitgupta/gokarna.git themes/gokarna
    echo "theme = 'gokarna'" >> hugo.toml
    ```

6. Finally, you can view your website by starting Hugo’s development server:
    ```bash
    hugo server
    ```
    - See your website at: [http://localhost:1313/](http://localhost:1313/)
    - Press `Ctrl+C` to stop the server

7. Last but not least, you will need to commit and push these changes to your GitHub repo and then deploy your website with GitHub pages. These Hugo docs explain the process best: https://gohugo.io/hosting-and-deployment/hosting-on-github/

## Conclusion

By following these instructions, you will be able to have a basic website up at `https://<YOUR_USERNAME>.github.io`. There is much more you can do to customize and add pages or posts to your website. These things may depend on which theme you chose, so I'll leave you to it to explore!

___

### More Resources
 - Hugo Quick Start guide: https://gohugo.io/getting-started/quick-start/
