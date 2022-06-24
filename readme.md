# Duplicate Image Finder

Duplicate image finder uses image hashing to find similar/duplicate images in your local storage. All you gotta do is

1. install
2. install dependencies (using `poetry`)
3. run it (using `poetry` maybe?)

For example:

```sh
# show help
python duplicate_finder.py --help
# add directory images and calculate hashes using 4 threads
python duplicate_finder.py --add <directory> --parallel 4
# show the duplicate/similar images found in your browser
python duplicate_finder.py --show
```
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
