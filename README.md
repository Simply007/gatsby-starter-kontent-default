# Gridsome Starter Kontent Lumen

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/Simply007/gridsome-starter-default-kontent/master/LICENSE)
[![Stack Overflow](https://img.shields.io/badge/Stack%20Overflow-ASK%20NOW-FE7A16.svg?logo=stackoverflow&logoColor=white)](https://stackoverflow.com/tags/kentico-cloud)
[![Live demo](https://img.shields.io/badge/-Live%20Demo-brightgreen.svg)](https://gridsome-starter-default-kontent.netlify.app/)

[![Netlify Status](https://api.netlify.com/api/v1/badges/f547d859-c6df-43fb-a936-97f7744cb2aa/deploy-status)](https://app.netlify.com/sites/gridsome-starter-default-kontent/deploys)

Bare-bones starter for [Gridsome](https://github.com/gridsome/gridsome). Basically clone of the [Default starter for Gridsome](https://github.com/gridsome/gridsome-starter-default) utilizing [Kentico Kontent](https://kontent.ai) as a data source vie [Gridsome source plugin for Kontent](https://gridsome.org/plugins/@meeg/gridsome-source-kentico-kontent).

![Page Screenshot](./screenshot.png)

## Getting Started

### Requirements

+ [Node.js](https://nodejs.org/)

### Install Gridsome CLI tool if you don't have

`npm install --global @gridsome/cli`

### Create codebase

1. Click on "Use this repository" button to [create your own repository from this template](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template).

### Create content source

1. Go to [app.kontent.ai](https://app.kontent.ai) and [create empty project](https://docs.kontent.ai/tutorials/set-up-kontent/projects/manage-projects#a-creating-projects)
1. Go to "Project Settings", select API keys and copy
    + Project ID
1. Install [Kontent Backup Manager](https://github.com/Kentico/kontent-backup-manager-js) and import data to newly created project from [`kontent-backup.zip`](./kontent-backup.zip) file (place appropriate values for `apiKey` and `projectId` arguments):

    ```sh
    npm i -g @kentico/kontent-backup-manager

    kbm --action=restore --apiKey=<Management API key>
        --projectId=<Project ID> --zipFilename=kontent-backup
    ```

    > Alternatively, you can use the [Template Manager UI](https://kentico.github.io/kontent-template-manager/import-from-file) for importing the content.

1. Go to your Kontent project and [publish all the imported items](https://docs.kontent.ai/tutorials/write-and-collaborate/publish-your-work/publish-content-items).

### Join codebase and content data

Copy [`.env.template`](`./.env.template`) and name it `.env` then set the `KONTENT_PROJECT_ID` environment variable to value from Kontent -> "Project Settings" ->  API keys -> Project ID.

**You are now ready to use the site as your own!**

## Development

Install the dependencies and run development environment

```sh
npm install  
npm run develop
```

## Site production build

Install the dependencies and run production build

```sh
npm install
npm run build
```

## Deploy with Netlify

Netlify can run in any frontend web environment, but the quickest way to try it out is by running it on a pre-configured starter site with Netlify. Use the button below to build and deploy your own copy of the repository:

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/Simply007/gridsome-starter-default-kontent)

After clicking that button, you’ll authenticate with GitHub and choose a repository name. Netlify will then automatically create a repository in your GitHub account with a copy of the files from the template. Next, it will build and deploy the new site on Netlify, bringing you to the site dashboard when the build is complete. Next, you’ll need to set up Netlify’s Identity service to authorize users to log in to the CMS.
