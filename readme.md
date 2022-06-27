# Duplicate Image Finder

Duplicate image finder uses image hashing to find similar/duplicate images in your local storage. All you gotta do is

1. install,
2. run (*will setup the database with table*) if no configuration is provided,
3. run specifying which directory to look for images, and finally
4. run asking it to show duplicate/similar images.

Please note that it is a prototype. Please use at your own discretion.

For example:

```sh
# 1. installing
python3.9 -m pip install --user duplicate-image-finder

# 2. show help
duplicate-image-finder --help

# 3. add directory images and calculate hashes using 4 threads
duplicate-image-finder --add <directory> --parallel 4

# 4. show the duplicate/similar images found in your browser
duplicate-image-finder --show
```

Running 4 will result in opening a browser that shows duplicate/similar images. If you click on delete, it will be moved to .Trash folder.


## Requirements

Lots, but all of them can be installed as dependencies as long as you are using `python3.9`. Unfortunately, some of its dependencies have not been made available in `python3.10` yet, so we are stuck there.

## Poetry

Installing dependencies

```sh
poetry install
```

Running

```sh
poetry run python duplicate_image_finder/duplicate_finder.py --show
```

Testing

```sh
poetry run pytest
```
etc.

This duplicate image finder source code is inspired/partially copied from https://github.com/philipbl/duplicate-images.git.

Significant changes from the referred version are:

1. moved from `mongodb` to `sqlite`
2. Is probably better in terms of finding similar images (or perhaps I misunderstood the previous code)

Concepts/Technologies I learned/tried to learn while doing this:

1. `poetry` for dependency
2. `pytest` for unit test
3. `pysqlite3` for database
4. `concurrency` for performance
5. `imagehash` for perpetual image hashing for finding similarity
6. grouping CLI arguments in python (mutually exclusive, etc) using `argparser`
