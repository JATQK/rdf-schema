# git2RDFLab-Schema

## Direct URLs
```
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform-github.ttl#> .
```

## PURLs
```
@prefix git: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform-github#> .
```

| Schema | Description |
|--|--|
| `git2RDFLab-git.ttl` | Contains clases for a Git representation of a repository, including branches, commits and diffs. |
| `git2RDFLab-platform.ttl` | Contains common base-classes for multiple external service platforms (tickets/issues). |
| `git2RDFLab-platform-github.ttl` | Contains specific classes and sub-classes extending the common platform classes for the named service (like Github, Gitlab, BitBucket, Jira). |

