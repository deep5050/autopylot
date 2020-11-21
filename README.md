![autopy-lot](https://socialify.git.ci/deep5050/autopy-lot/image?description=1&descriptionEditable=github%20action%20to%20convert%20jupyter%20notebooks%20to%20various%20formats&font=Source%20Code%20Pro&forks=1&issues=1&logo=https%3A%2F%2Fi.imgur.com%2FWZSNO5m.png&pattern=Signal&pulls=1&stargazers=1&theme=Light)


![test-markdown](https://github.com/deep5050/autopy-lot/workflows/test-markdown/badge.svg)
![test-py](https://github.com/deep5050/autopy-lot/workflows/test-py/badge.svg)
![vistors](http://hits.dwyl.com/deep5050/autopy-lot.svg)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fdeep5050%2Fautopy-lot.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fdeep5050%2Fautopy-lot?ref=badge_shield)

## conversions:
1. .ipynb -> .md
2. .ipynb -> .py   <b>(DEFAULT)</b>
3. .py -> .ipynb

### NOTE
``R`` support will be added soon. Please don't try to convert R files for now.

## USAGE

create a ``autopy-lot.yml`` file under ``.github/workflows`` with the following contents:
### Default configuration

```yaml
name: autopy-lot
on: [push]

jobs:
  build:
    name: autopy-lot
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - name: autopy-lot 
        uses: deep5050/autopy-lot@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN}}
          output_dir: './autopy-lot/'
```
### Advanced configuration

```yaml
name: autopy-lot
on: [push]

jobs:
  build:
    name: autopy-lot
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - name: autopy-lot 
        uses: deep5050/autopy-lot@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN}}
          check:
          input_type:
          comment_magics:
          split_at_heading:
          output_type:
          output_dir: './autopy-lot/'


```
### Input options

``check``  : ``all`` to convert all specified files (based on file type) on every run. ``latest`` to convert only the files changed on last commit.

``input_types`` : ``py`` ``ipynb`` ``r``

``comment_magics`` : ``true`` see jupytext documentation for further details.

``split_at_heading`` : ``true`` see jupytext documentation for further details.


``output_type`` : ``py`` ``markdown`` ``r`` ``ipynb``


``output_dir``: give a output directory name where all the converted outputs will be stored. default is ``./autopy-lot/``. when provide custom path name, make sure the to put the initial ``.`` and ``/`` at the end. please note that it is a mandatory input argument.


## Note

This action can handle only one type of conversion per workflow setup.
If you need to convert input files to different file types, you need to create several ``.yml`` files under ``.github/workflows``.

Example :

``autopy-lot-markdown.yml`` , ``autopy-lot-py.yml``.

## License

>MIT License

>Copyright (c) 2020 Dipankar Pal

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fdeep5050%2Fautopy-lot.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fdeep5050%2Fautopy-lot?ref=badge_large)

## Thanks
Icons made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>