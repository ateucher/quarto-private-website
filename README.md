# Create a password-protected Quarto website

This is a Quarto website template with password protection, using the 
[staticryptR](https://github.com/nikitoshina/staticryptR) package.

This will encrypt the rendered website and put it behind a simple password
prompt. It does not encrypt the source files, they will still be visible if they
are in a public repository, so this is likely most useful if the source files
are in a private repository but GitHub pages is set to be public (e.g., for 
[GitHub Enterprise Cloud users](https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site)).

Using staticryptR requires Node and the [staticrypt](https://github.com/robinmoisson/staticrypt) 
Node library to be installed on your computer:

- Install [Node](https://nodejs.org/en/download) for your operating system.

In R:

- Install [staticryptR](https://github.com/nikitoshina/staticryptR)

    ```
    install.packages("staticryptR")
    ```

- Run the following to install the `staticrypt` Node library:

    ```
    staticrytR::install_staticrypt()
    ```

`encrypt.R` contains the script that will do the encryption. Set options and 
your password in that file (again note that this file will be visible if your 
repo is public). This script will be run automatically when the site is rendered
by `quarto render` or `quarto preview` - it is specified in the `post-render` 
paramater in `_quarto.yml`.

After it is rendered, when you visit your site it will present you with a 
password prompt:

![Screenshot of a window prompting for a passward](password-page.png)

Enter the password. `staticrypt` encrpyts each page individually, which means
you will need to enter your password each time you visit each page on the site,
which can become tedious. If you click the "remember me" checkbox, it will
avoid you having to do this.

By default this template stores and encripts the rendered site in the `docs/`
directory in the main branch. To render to the `gh-pages` branch and publish
via a GitHub action, without needing to install Node on your computer, see the
repository template at 
[ateucher/quarto-private-github-actions](https://github.com/ateucher/quarto-private-gh-actions).
