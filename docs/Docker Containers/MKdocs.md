# MkDocs and material 

## Why do I run this?
I run MKdocs on material to make hte best attempt at taking notes while I deploy things and that way I can remember what I did. This is a beautiful customized interface that allows me to pump out notes and easily review them like a wiki. 

## My install

1. Made a directory to retain all my docs 

    ``` 
    mkdir mkdocs
    ```

2. Changed into that directory  
    ```
    cd mkdocs
    ```

3. Ran this command to download the image  
    ```
    docker pull squidfunk/mkdocs-material
    ```

4. Followed up with this to create the container and start creating  
    ```
     sudo docker run --rm -it -p 8000:8001 -v "$(PWD):/docs" squidfunk/mkdocs-material --restart unless-stopped redis
    ```

5. Once this I started customiztion with the help of this [site](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/)


## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## Source 

For full documentation visit [mkdocs.org](https://www.mkdocs.org).