# Ten Simple Rules for Deep Learning in Biology

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://Benjamin-Lee.github.io/deep-rules/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://Benjamin-Lee.github.io/deep-rules/manuscript.pdf)
[![Build Status](https://travis-ci.org/Benjamin-Lee/deep-rules.svg?branch=master)](https://travis-ci.org/Benjamin-Lee/deep-rules)
[![Twitter URL](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Have%20you%20used%20deep%20learning%20in%20your%20research%3F%20If%20so%2C%20contribute%20to%20the%20Ten%20Simple%20Rules%20for%20Deep%20Learning%20in%20Biology%20paper%21%0A%0Ahttp%3A%2F%2Fgithub.com%2FBenjamin-Lee%2Fdeep-rules)

## Manuscript description

<!-- usage note: edit this section. -->

This is the manuscript for a community-written [Ten Simple
Rules](https://collections.plos.org/ten-simple-rules) article aimed at [PLOS
Computational Biology](https://journals.plos.org/ploscompbiol/). Deep learning is exploding in
popularity and is increasingly finding its way into biological data analysis.
However, since most biologists receive little (or no) data science training,
using deep learning properly can be a daunting task.

**We're going to try to fix that.** By boiling down the community's knowledge
into ten simple rules, we hope to increase the number of biological researchers
using DL (by making it more inviting) and the quality of the research (by
helping them avoid common mistakes).

Join us!

## Where we are now

Currently, we're in the process of drafting the paper with each rule being tracked in its own [project](https://github.com/Benjamin-Lee/deep-rules/projects). To contribute to the paper, take a look at [`CONTRIBUTING.md`](CONTRIBUTING.md) for information on how we're organizing the writing as well as [`USAGE.md`](USAGE.md) for instructions on how to write the actual text.

The raw text of the manuscript is stored within the [content directory](content). The rendered manuscript may be viewed as HTML [here](https://Benjamin-Lee.github.io/deep-rules/) or as a PDF [here](https://Benjamin-Lee.github.io/deep-rules/manuscript.pdf).

The [presubmission inquiry](content/presubmission_inquiry.md) has been submitted and we're eagerly waiting to hear back from the journal.

## How you can help

Help of any kind is highly appreciated. Want to pitch in but not sure how?

- Help us write the [rules](rules.md) into a [manuscript](content).
- Know of anyone who might be interested? [Send them an email!](mailto:@?subject=Ten%20Simple%20Rules%20for%20Using%20Deep%20Learning%20in%20Biology%20paper&body=Take%20a%20look%20at%20the%20Deep%20Rules%20project%2C%20a%20PLOS%20Computational%20Biology%20paper%20written%20collaboratively%20using%20GitHub!%20%0A%0Ahttps%3A%2F%2Fgithub.com%2FBenjamin-Lee%2Fdeep-rules%0A%0AIf%20you%20know%20of%20anyone%20who%20might%20be%20interested%2C%20feel%20free%20to%20forward%20this%20email%20along!)
- Have Twitter followers? [Tweet about the project!](https://twitter.com/intent/tweet?text=Have%20you%20used%20deep%20learning%20in%20your%20research%3F%20If%20so%2C%20contribute%20to%20the%20Ten%20Simple%20Rules%20for%20Deep%20Learning%20in%20Biology%20paper%21%0A%0Ahttps%3A%2F%2Fgithub.com%2FBenjamin-Lee%2Fdeep-rules)

For more information, see [the contribution guidelines](CONTRIBUTING.md). All contributions are subject to the [code of conduct](CODE_OF_CONDUCT.md).

## Manubot

<!-- usage note: do not edit this section -->

Manubot is a system for writing scholarly manuscripts via GitHub.
Manubot automates citations and references, versions manuscripts using git, and enables collaborative writing via GitHub.
The [Manubot Rootstock repository](https://git.io/vQSvo) is a general purpose template for creating new Manubot instances, as detailed in [`SETUP.md`](SETUP.md).
See [`USAGE.md`](USAGE.md) for documentation how to write a manuscript.

Please open [an issue](https://github.com/Benjamin-Lee/deep-rules/issues) for questions related to Manubot usage, bug reports, or general inquiries.

### Repository directories & files

The directories are as follows:

+ [`content`](content) contains the manuscript source, which includes markdown files as well as inputs for citations and references.
  See [`USAGE.md`](USAGE.md) for more information.
+ [`output`](output) contains the outputs (generated files) from the manubot including the resulting manuscripts.
  You should not edit these files manually, because they will get overwritten.
+ [`webpage`](webpage) is a directory meant to be rendered as a static webpage for viewing the HTML manuscript.
+ [`build`](build) contains commands and tools for building the manuscript.
+ [`ci`](ci) contains files necessary for deployment via continuous integration.
  For the CI configuration, see [`.travis.yml`](.travis.yml).

### Local execution

To run the Manubot locally, install the [conda](https://conda.io) environment as described in [`build`](build).
Then, you can build the manuscript on POSIX systems by running the following commands.

```sh
# Activate the manubot conda environment (assumes conda version >= 4.4)
conda activate manubot

# Build the manuscript, saving outputs to the output directory
sh build/build.sh

# At this point, the HTML & PDF outputs will have been created. The remaining
# commands are for serving the webpage to view the HTML manuscript locally.

# Configure the webpage directory
python build/webpage.py

# View the manuscript locally at http://localhost:8000/
cd webpage
python -m http.server
```

Sometimes it's helpful to monitor the content directory and automatically rebuild the manuscript when a change is detected.
The following command, while running, will trigger both the `build.sh` and `webpage.py` scripts upon content changes:

```sh
sh build/autobuild.sh
```

### Continuous Integration

[![Build Status](https://travis-ci.org/Benjamin-Lee/deep-rules.svg?branch=master)](https://travis-ci.org/Benjamin-Lee/deep-rules)

Whenever a pull request is opened, Travis CI will test whether the changes break the build process to generate a formatted manuscript.
The build process aims to detect common errors, such as invalid citations.
If your pull request build fails, see the Travis CI logs for the cause of failure and revise your pull request accordingly.

When a commit to the `master` branch occurs (for example, when a pull request is merged), Travis CI builds the manuscript and writes the results to the [`gh-pages`](https://github.com/Benjamin-Lee/deep-rules/tree/gh-pages) and [`output`](https://github.com/Benjamin-Lee/deep-rules/tree/output) branches.
The `gh-pages` branch uses [GitHub Pages](https://pages.github.com/) to host the following URLs:

+ **HTML manuscript** at https://Benjamin-Lee.github.io/deep-rules/
+ **PDF manuscript** at https://Benjamin-Lee.github.io/deep-rules/manuscript.pdf

For continuous integration configuration details, see [`.travis.yml`](.travis.yml).

## License

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Except when noted otherwise, the entirety of this repository is licensed under a CC BY 4.0 License ([`LICENSE.md`](LICENSE.md)), which allows reuse with attribution.
Please attribute by linking to https://github.com/Benjamin-Lee/deep-rules.

Since CC BY is not ideal for code and data, certain repository components are also released under the CC0 1.0 public domain dedication ([`LICENSE-CC0.md`](LICENSE-CC0.md)).
All files matched by the following glob patterns are dual licensed under CC BY 4.0 and CC0 1.0:

+ `*.sh`
+ `*.py`
+ `*.yml` / `*.yaml`
+ `*.json`
+ `*.bib`
+ `*.tsv`
+ `.gitignore`

All other files are only available under CC BY 4.0, including:

+ `*.md`
+ `*.html`
+ `*.pdf`
+ `*.docx`

Except for the following files with different licenses:

+ `build/assets/anchors.js` which is [released](https://www.bryanbraun.com/anchorjs/) under an [MIT License](https://opensource.org/licenses/MIT)

Please open [an issue](https://github.com/Benjamin-Lee/deep-rules/issues) for any question related to licensing.
