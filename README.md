# FAO Schwarz

FAO Schwarz is the codebase for the ecommerce site hosted at https://faoschwarz.com/

The site is hosted on Shopify. It uses the Shopify theme [Impulse](https://themes.shopify.com/themes/impulse/styles/modern)

## Prerequisites

Before you begin, ensure you have met the following requirements:

* You have installed Python 3.0
* You have installed [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* You have (free) [Shopify partner](https://www.shopify.com/partners) account
* You have an empty store created on your Shopify account

## Setting up Themekit for local development

Shopify does not have a fully local development setup, meaning you cannot run the store on a server locally at `localhost`. Themekit lets you write code locally and have it sync to your personal Shopify store so that you can preview your changes live.

☢️ When running Themekit `watch`, everytime you hit save, Themekit pushes your changes to the store that you are pointing to. So, make very sure that the store you are pointing to is your personal Partner store. You must never accidentally point to a QA or Staging store.

### Install Themekit
#### macOS Installation
Use homebrew to install Theme Kit by running the following commands.
```
brew tap shopify/shopify
brew install themekit
```

#### Windows Chocolatey Installation
If you have chocolatey installed you can install themekit by running the following commands.
```
choco install themekit
```

#### Linux Installation
If you are on linux based system, you can use the following installation script to automatically download and install the latest Theme Kit for you.
```
curl -s https://shopify.github.io/themekit/scripts/install.py | sudo python
```

Ensure that it works as expected by running `theme version`

### Get Shopify API Access
In order to write code and test it on your personal Shopify partner account, you need to set up Shopify API access first. Here are the steps:

1. In the store’s Shopify admin, click Apps.
2. Near the bottom of the page, click on Manage private apps.
3. If you see a notice that “Private app development is disabled”, then click “Enable private app development”.
4. Click Create new private app.
5. In the App details section, fill out the app name and your email address.
6. In the Admin API section, click Show inactive Admin API permissions.
7. Scroll to the “Themes” section and select Read and write from the dropdown.
8. Click Save.
9. Read the private app confirmation dialog, then click Create app.
10. You’ll return to the app detail page. Your new, unique access credentials are visible in the Admin API section. Copy the password. You’ll use it in the next step.

### Get Theme ID

A store can have multiple themes. To select the particular theme that want to work on you need the theme’s ID number. The easiest way to get your theme’s ID number is to use the get command like this:

```
theme get --list -p=[your-password] -s=[you-store.myshopify.com]
```

## Installing FAO Schwarz

Once you have your Shopify Partner store password, your store URL and the Theme ID you can clone this theme to your system. To install FAO Schwarz to your local, follow these steps:

On your command line interface navigate to your working directory and clone this repository.
```
cd Documents/workspace
git clone https://github.com/merchsource/faoschwarz.git
```

## Create a config file
In the root of this project create a file named `config.yml`. This file will contain a list of environments that you can point to. By default Themekit will use the theme titled `development`

```
development:
  password: [Shopify API Password]
  theme_id: "[Theme ID]"
  store: [Store URL e.g. your-store.myshopify.com]
  timeout: 1m0s
```

This is your personal config file and should never be committed to the codebase. It is added to the .gitignore file by default so that won't happen by accident.

## Contributing to FAO Schwarz
<!--- If your README is long or you have some specific process or steps you want contributors to follow, consider creating a separate CONTRIBUTING.md file--->
To contribute to <project_name>, follow these steps:

1. Fork this repository.
2. Create a branch: `git checkout -b <branch_name>`.
3. Make your changes and commit them: `git commit -m '<commit_message>'`
4. Push to the original branch: `git push origin <project_name>/<location>`
5. Create the pull request.

Alternatively see the GitHub documentation on [creating a pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).

## Contributors

Thanks to the following people who have contributed to this project:

* [@ahmad-gspann](https://github.com/ahmad-gspann) 
* [@ankush-gspann](https://github.com/ankush-gspann) 
* Dipti Bhardwaj
* [@rahulgspann](https://github.com/rahulgspann) 
* [@Sagar Mahajan](https://github.com/sagar-GSPANN)
* [@sapchak](https://github.com/sapchak)


You might want to consider using something like the [All Contributors](https://github.com/all-contributors/all-contributors) specification and its [emoji key](https://allcontributors.org/docs/en/emoji-key).

## Contact

Chris Graves <chris.graves@merchsource.com>
