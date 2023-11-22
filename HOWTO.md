# How to set up and run our JupyterBook

The following section, from The Turing Way, illustrates the reasons why you'd want to build our JupyterBook locally:

> It’s always handy to be able to preview any changes you have been working on as you go - you can be confident that changes you have made are accurate and as intended. A nice way to do this is to use the underlying Jupyter Book tool to build the book locally.
>
> This is useful because it allows you to preview any changes you have made on your local machine before you push your changes to a remote branch. You can then decide if you are happy with the result and push your changes to the remote branch thus helping to keep Pull Request conversations and commit histories a bit cleaner.

## Step-by-step guide

1. Install miniconda by following the instructions for your Operating System (Windows, MacOS, Linux) at this link: https://conda.io/projects/conda/en/latest/user-guide/install/index.html#regular-installation

2. Open your terminal app and run the `conda init` command in your terminal. You should see (base) in your prompt indicating that conda was successfully installed and you are now in its base environment.

3. Create a new environment and install a modern version of Python into it:

    ```bash
    $ conda create --name tric-dt python=3.10
    ...
    ```

4. Activate the environment with `conda activate tric-dt`. Any commands we run with Python or pip from now on will use the versions of Python and pip installed into this conda environment, not any others.

5. Clone The Turing Way repository from GitHub to your machine using the command:

    ```bash
    $ git clone https://github.com/alan-turing-institute/tric-dt
    ...
    ```

6. Navigate into the cloned repository folder using the command `cd tric-dt`, where the cd command means change directory.

7. Then change into the sub-directory the website is built from using `cd tric-dt-book`

8. Our JupyterBook is built using multiple python libraries. We can install these dependencies into your conda environment using the following command:

    ```bash
    $ pip install -r requirements.txt
    ...
    ```

    The `requirements.txt` file contains all the dependencies that are required to build our JupyterBook.

9. Now you can build the book:

    ```bash
    $ jupyter-book build .
    ```

10. The output of the build process will provide output such as below that demonstrate how you can view the book locally:

    ```bash
    ===============================================================================

    Finished generating HTML for book.
    Your book's HTML pages are here:
        _build/html/
    You can look at your book by opening this file in a browser:
        _build/html/index.html
    Or paste this line directly into your browser bar:
        file:///[...]/tric-dt/tric-dt-book/_build/html/index.html

    ===============================================================================
    ```

### Build the book while working on a Pull Request

If you would like to preview a version of the book from a certain branch (perhaps to render the book while working on a PR) then simply switch to the required branch and rebuild the book as in step 9:

```bash
$ git checkout mybranch
...

$ jupyter-book build .
...
```

Follow the link as before and you will see changes specific to that branch rendered.
