# caltechdata_feeds

caltechdata_feeds queries the caltechDATA (Invenio 3) API, returns metadata, and 
saves for library feeds project

Requirements:
- Dataset (https://github.com/caltechlibrary/dataset)
- Python 3

Initialization:
    Create a collection by typing
    ```shell
    dataset init caltechdata
    export DATASET=caltechdata
    ```

## Usage

```shell
   python caltechdata_feeds.py [-h]
```

optional arguments:
  -h, --help  show this help message and exit


## Metadata Mapping

Field mapping for feeds

- Title: metadata.title
- Authors: metadata.authors
This is an array containing .authorName, .authorAffiliation, and .authorIdentifiers
.authorIdentifiers is an array containing .authorIdentifier and .authorIdentifierScheme
- Description: metadata.descriptions
This is a array containing .descriptionType and .descriptionValue
- Embargo Date: metadata.embargo_date
Could also get from metadata.access_rights=="embargoed"
- Publication Date: metadata.publicationDate
- Link: metadata.doi
Will need to prepend with https://doi.org/
- Funder: metadata.fundings
This is an array containing .fundingName and .fundingAwardNumber
- Keywords: metadata.subjects
