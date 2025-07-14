**# GitLotus Vocabularies**

Four vocabularies are established separating the different domain scopes.

**## Current Version (v2) - Recommended**

1. `git2RDFLab-git.ttl`: The GitLotus base ontology provides entities found in a Git repository (commits, branches, diffs).
2. `git2RDFLab-platform.ttl`: The GitLotus platform ontology provides entities found in external git platform providers (issues, users, comments).
3. `git2RDFLab-platform-github.ttl`: Contains specific classes and sub-classes extending the common platform classes for GitHub.
4. `git2RDFLab-rating.ttl`: The GitLotus rating ontology provides structured evaluation and rating capabilities.

The vocabularies are available as follows.

**## Permanent URLs (PURLs)**

```
@prefix git: <https://purl.archive.org/git2rdf/v2/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform-github#> .
@prefix rating: <https://purl.archive.org/git2rdf/v2/git2RDFLab-rating#> .
```

**## Direct URLs**

```
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform-github.ttl#> .
@prefix rating: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-rating.ttl#> .
```

**## Legacy Version (v1) - Deprecated**

⚠️ **Version 1.0 is deprecated. Use v2 for new projects.**

1. `git2RDFLab-git.ttl`: The GitLotus base ontology provides entities found in a Git repository (mainly commits).
2. `git2RDFLab-platform.ttl`: The GitLotus platform ontology provides entities found in external git platform providers, mainly issues or user handles.
3. `git2RDFLab-platform-github.ttl`: Contains specific classes and sub-classes extending the common platform classes for the named service (like Github, Gitlab, BitBucket, Jira).

**## Permanent URLs (PURLs)**

```
@prefix git: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform-github#> .
```

**## Direct URLs**

```
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform-github.ttl#> .
```