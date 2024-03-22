# PHP Lint GitHub Action

This Github Action runs `php -l` on all PHP files found in the current project. It allows you to easily and quickly check for 
any syntax / parse errors in your PHP files on pull requests or pushes. This is especially useful for code that is 
meant to run on multiple PHP versions.  

---

## Getting Started

Using this action to check for syntax / parse errors for PHP versions 7.4, 8.0, and 8.3 can be done with the following template:

```
steps:
  - name: Checkout
    uses: actions/checkout@v4
    with:
      fetch-depth: 0
  - name: PHP Lint 7.4
    uses: dbfx/github-phplint/7.4@master
    with:
      folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
  - name: PHP Lint 8.0
    uses: dbfx/github-phplint/8.0@master
    with:
      folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
  - name: PHP Lint 8.3
    uses: dbfx/github-phplint/8.3@master
    with:
      folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
```

---

## Brand New Setup

If you have never used github actions, then create a file called phplint.yml in your Git repository in the directory 
.github/workflows. Inside of .github/workflows/phplint.yml put the following text:
```
name: PHP Linting

on: push

jobs:
  phplint:

    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0
      - name: PHP Lint 7.2
        uses: dbfx/github-phplint/7.2@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
      - name: PHP Lint 7.3
        uses: dbfx/github-phplint/7.3@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
      - name: PHP Lint 7.4
        uses: dbfx/github-phplint/7.4@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
      - name: PHP Lint 8.0
        uses: dbfx/github-phplint/8.0@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""   
      - name: PHP Lint 8.1
        uses: dbfx/github-phplint/8.1@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
      - name: PHP Lint 8.2
        uses: dbfx/github-phplint/8.2@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
      - name: PHP Lint 8.3
        uses: dbfx/github-phplint/8.3@master
        with:
          folder-to-exclude: "! -path \"./vendor/*\" ! -path \"./folder/excluded/*\""
```

If you want to run the lint on Pull Requests instead of pushes change the ```on: push``` to ```on: pull```.

In the above example, your workflow will run the PHP syntax check with PHP 5.6, 7.2 & 7.3. You may remove any of these that do not apply.

---

## Supported versions

Right now there is support for the following PHP versions: 
 - 5.5
 - 5.6
 - 7.2
 - 7.3
 - 7.4
 - 8.0
 - 8.1
 - 8.2
 - 8.3
 
 If you would like to add more submit a PR or an issue. 
 
---

## Ignoring paths

You can see in the above examples it ignores certain paths. You may add as many as you need by copying the example. 
The action ignores the folder `vendor` at root of project by default.

---

## Original work

This is based on PrestaShop's original work https://github.com/PrestaShopCorp/github-action-php-lint. 
 
