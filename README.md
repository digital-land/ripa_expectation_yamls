# ripa expectation yamls

This repo was created to save the first version of expectation files for the RIPA datasets.

Each yaml file has a collection of expectations that should be run against the dataset with the same name (e.g. listed_building.yaml should be run against listed_building.sqlite3)

The folder "expectations_results" has one folder for each of the datasets named accordingly, inside each folder you find one json file for each data quality expectation run, the name of the files will inform if the expectation succeeded (data quality as expected) or failed (problem with data quality). Inside each json file you will find all details needed to understand better any failed expectation (e.g. what was the dataset, what was the expectation, what exactly were the arguments passed to the expectation, what exactly was expected and what exactly was found, etc). The results saved in this folder reflect the status of the data as it was in the versions used when writting the expectations (15 Aug 2022).

More information about how expectation yamls should be used via the expectation tool (now usable from inside the Digital-Land-Python package) can be found at: https://github.com/digital-land/digital-land-python/tree/main/digital_land/expectations

The datasets used to run the data quality tests stored here were obtained from the S3 buckets where they are saved by the collection pipelines.

## Status

- For most of the dataset expectation yamls, they will contain an initial set of data quality expectations that was written taking in consideration general information about the datasets and contents of the specification repos.

- For the "article-4-direction-area" yaml also re-wrote most of the tests that are made via the API (https://digital-land-performance.herokuapp.com/ripa/) to be made via the expectations tool. We say most because a few of them used information or functionality that is available at the API but was not available in the dataset stage and spacialite. Note that a few tests were kept commented because at the time of writting they were failing in the herokuapp so we saw no advantage of having them running via the expectation during the development stage (they can easily be un-commented if one wished them to run anyway).
