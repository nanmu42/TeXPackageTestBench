# What's this?

This is a docker image of MiKTeX Ubuntu distribution, with GNU make, latexmk, amsfont, and fandol.

# Why is this?

For a lone time, doing continuous integration (CI) on packages and classes for LaTeX and friends is always a challenge - a package/class does not live alone, which means there are always dependencies. Sorting out dependencies manually can get your hands dirty.

Luckily, one compelling feature of MiKTeX is building on the fly - dependencies get sorted automatically. That's why we have this lovely piece of docker image here.

# How to use this?

Pull the image and off you go.

```shell
docker pull nanmu42/tex-package-test-bench

# create a volume for packages going to be installed on the fly
docker volume create --name packages

# expose your working directory to /miktex/work
# latexmk, latex, pdflatex, xelatex, make... handy tools are all supported
docker run -it -v packages:/miktex/.miktex -v $(pwd):/miktex/work nanmu42/tex-package-test-bench latexmk yourFile.tex
```

# Cool, but I want a example

Click [here](https://github.com/nanmu42/CQUThesis/blob/master/.travis.yml).

# How is the paperwork thing?

This image is barely a composition of human intelligence works listed below (thanks for the fabulous!):

* [Docker](https://www.docker.com/)
* [Ubuntu](https://www.ubuntu.com/)
* [MiKTeX](https://miktex.org/)
* [latexmk](https://ctan.org/pkg/latexmk)
* [GNU make](https://www.gnu.org/software/make/)
* and more...

Copyrights belong to them respectively.

Use of these works may be restricted by their license respectively.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
