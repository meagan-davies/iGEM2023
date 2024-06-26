# Team Calgary 2023 Wiki

This repository **MUST** contain all coding assets to generate your team's wiki (HTML, CSS, JavaScript, TypeScript, Python, etc).

Images, photos, icons and fonts **MUST** be stored on `static.igem.wiki` using [uploads.igem.org](https://uploads.igem.org), and Videos **must** be embedded from [iGEM Video Universe](https://video.igem.org).

For up-to-date requirements, resources, help and guidance, visit [competition.igem.org/deliverables/team-wiki](https://competition.igem.org/deliverables/team-wiki).

## Getting started

You should probably only edit the files inside folders `static`, `wiki` and `wiki > pages`.
1. Open the Web IDE
1. Make the changes on the files you wish:
    * For the menu, change the file [menu.html](wiki/menu.html)
    * For the layout, change the file [layout.html](wiki/layout.html)
    * For the pages, change the corresponding file in the foler [pages](wiki/pages)
1. Review the changes you made
1. Once you are done, save the changes by **committing** them to the *main branch* of the repository
1. An automated script will build, test and deploy your wiki, which should take less than 30 seconds.

## About this Template

### Files

The static assets are in the `static` directory. The layout and templates are in the `wiki` directory, and the pages live in the `wiki > pages` directory. Unless you are an experienced and/or adventurous human, you probably shouldn't change other files.

    |__ static/             -> static assets (CSS and JavaScript files only)
    |__ wiki/               -> Main directory for the pages and layouts
        |__ footer.html     -> Footer that will appear in all the pages
        |__ layout.html     -> Main layout of your wiki. All the pages will follow its structure
        |__ menu.html       -> Menu that will appear in all the pages
        |__ pages/          -> Directory for all the pages
            |__ *.html      -> Actual pages of your wiki
    |__ .gitignore          -> Tells GitLab which files/directories should not be uploaded to the repository
    |__ .gitlab-ci.yml      -> Automated flow for building, testing and deploying your website.
    |__ LICENSE             -> License CC-by-4.0, all wikis are required to have this license - DO NOT MODIFY
    |__ README.md           -> File containing the text you are reading right now
    |__ app.py              -> Python code managing your wiki
    |__ dependencies.txt    -> Software dependencies from the Python code

### Technologies

  * [GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/)
  * [Python](https://www.python.org): Programming language
  * [Flask](https://palletsprojects.com/p/flask/): Python framework
  * [Fronzen-Flask](https://pythonhosted.org/Frozen-Flask): Library that builds the wiki to be deployed as a static website
  * [Bootstrap](https://getbootstrap.com/docs/5.0/components): CSS and JS components used
### Building Locally

To work locally with this project, follow the steps below:

#### Install

* Using vscode the repository can be cloned from github
* Next create a virtual environment by running:
```bash
python3 -m venv venv
. venv/bin/activate # on Linux, MacOS; or
. venv\Scripts\activate # on Windows
pip install -r dependencies.txt
```

#### Execute Locally

* To run the website open a terminal and run:
```bash
python app.py
```
* In browser of choice run http://0.0.0.0:8080 or http://localhost:8080/

### Using GitHub

* Note when using GitHub Git commands are used to control the movement of data
* To push and pull code in the repository
    - To push code: Use Source Control in side panel to commit changes to the respository and label updates
    - To pull code: Open a bash terminal and run
```bash
git pull
```
* Note branches can be used to contain updates and prevent overwriting updates
    - When merging branches it is important to avoiding overwriting code

#### Vscode Extensions

* Note to simplify the use of GitHub in Vscode the following extensions are utlised:
    - Git Extension Pack
    - GitHub Codespaces
    - GitHub Pull Requests
 
#### Building/Using Frozen Flask

* To freeze the website such that it can be deployed using github pages download then following dependencies:
```bash
pip install frozen-flask
pip install flask_flatpages
```
* Reference app.py for building features using frozen-flask and flatpages to freeze the webpages.
* To build/freeze the webpage run:
```bash
python app.py build
```
* Then rename the generated folder "docs".
* In the github repository configure the settings under pages such that it builds/deploys from the docs/ folder.
