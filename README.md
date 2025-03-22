<a href="https://github.com/git2RDFLab/"><img align="right" role="right" height="96" src="https://github.com/git2RDFLab/.github/blob/main/profile/images/GitLotus-logo.png?raw=true" style="height: 96px;z-index: 1000000" title="GitLotus" alt="GitLotus"/></a>

# GitLotus Vocabularies 

Three vocabularies are established separating the different domain scopes.

1. `git2RDFLab-git.ttl`: The GitLotus base ontology provides entities found in a Git repository (mainly commits).
2. `git2RDFLab-platform.ttl`: The GitLotus platform ontology provides entities found in external git platform providers, mainly issues or user handles.
3. `git2RDFLab-platform-github.ttl`: Contains specific classes and sub-classes extending the common platform classes for the named service (like Github, Gitlab, BitBucket, Jira).

The vocabularies are available as follows.

## Permanents URLs (PURLs)

```
@prefix git: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform-github#> .
```

## Direct URLs

```
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform-github.ttl#> .
```

