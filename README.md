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
