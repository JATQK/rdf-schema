<a href="https://github.com/git2RDFLab/"><img align="right" role="right" height="96" src="https://github.com/git2RDFLab/.github/blob/main/profile/images/GitLotus-logo.png?raw=true" style="height: 96px;z-index: 1000000" title="GitLotus" alt="GitLotus"/></a>

# GitLotus Vocabularies 

> **⚠️ Version 1 Deprecated**: v1 vocabularies are deprecated. Please use v2 for new projects. See [v1 (Deprecated)](#v1-deprecated) section below.

Four vocabularies are established separating the different domain scopes with enhanced extensibility and cross-platform support in v2:

1. `git2RDFLab-git.ttl`: The GitLotus base ontology provides entities found in a Git repository (mainly commits).
2. `git2RDFLab-platform.ttl`: The GitLotus platform ontology provides entities found in external git platform providers, with **open extensible enumerations** and **consistent union patterns** for cross-platform compatibility.
3. `git2RDFLab-platform-github.ttl`: Contains specific classes and sub-classes extending the common platform classes for GitHub, demonstrating the extensibility patterns.
4. `git2RDFLab-analysis.ttl`: **NEW in v2** - Comprehensive analysis and metrics ontology for code quality, security, performance, and repository analytics.

## Key v2 Improvements

- **Comprehensive Platform Ontology**: Expanded from minimal 45-line v1 to full 579-line platform ontology with workflows, reviews, comments, and reactions
- **PROV-O Integration**: Full provenance tracking with PROV-O Entity and Activity subclasses throughout
- **Analysis Framework**: NEW dedicated analysis ontology (526 lines) for metrics, results, and LLM-based analysis
- **SHACL Validation**: NEW comprehensive shape constraints for all ontologies (1,500+ lines of validation rules)
- **GitHub Specialization**: Enhanced GitHub-specific extensions with proper inheritance patterns

## Current Version (v2) - Recommended

### Permanent URLs (PURLs)

```turtle
@prefix git: <https://purl.archive.org/git2rdf/v2/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform-github#> .
@prefix analysis: <https://purl.archive.org/git2rdf/v2/git2RDFLab-analysis#> .
```

### Direct URLs

```turtle
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform-github.ttl#> .
@prefix analysis: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-analysis.ttl#> .
```

### SHACL Shapes

#### Permanent URLs (PURLs)

```turtle
@prefix git-shape: <https://purl.archive.org/git2rdf/v2/git2RDFLab-git-shape#> .
@prefix platform-shape: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform-shape#> .
@prefix github-shape: <https://purl.archive.org/git2rdf/v2/git2RDFLab-platform-github-shape#> .
@prefix analysis-shape: <https://purl.archive.org/git2rdf/v2/git2RDFLab-analysis-shape#> .
```

#### Direct URLs

```turtle
@prefix git-shape: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-git-shape.ttl#> .
@prefix platform-shape: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform-shape.ttl#> .
@prefix github-shape: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-platform-github-shape.ttl#> .
@prefix analysis-shape: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v2/git2RDFLab-analysis-shape.ttl#> .
```


## Platform Coverage

The v2 ontology provides a comprehensive foundation for Git hosting platforms:

```turtle
# Core platform concepts with string-based states
platform:ticket123 a platform:Ticket ;
    platform:state "open" ;  # Expected: open, closed, merged, draft
    platform:title "Fix authentication bug" .

platform:workflow456 a platform:WorkflowExecution ;
    platform:status "in_progress" ;  # Expected: queued, in_progress, completed, etc.
    platform:conclusion "success" .  # Expected: success, failure, cancelled, etc.

# GitHub specialization
github:issue789 a github:Issue ;
    rdfs:subClassOf platform:Ticket ;
    platform:state "closed" .
```

## Analysis & Metrics Framework

The analysis ontology provides a structured framework for representing analysis results and metrics with full PROV-O integration.

### Core Components

- **Analysis Results**: Store analysis outcomes with values, timestamps, and execution context
- **Metrics**: Reusable metric definitions with instructions, categories, and expected scales  
- **Executions**: Group related analysis results with scope and configuration management
- **Agents**: Human and automated agents performing analysis with attribution tracking
- **LLM Configuration**: Specialized support for Large Language Model analysis with token tracking

### Measurement Framework

- **Multi-type Values**: Support for integer, decimal, string, and boolean result values
- **Measurement Scales**: Ordinal, interval, ratio, and categorical scale types
- **Confidence & Feedback**: Optional confidence scores and explanatory feedback for results
- **Cross-domain Relations**: Generic properties for linking any resource to analysis results

### Examples

```turtle
# Human analysis example
analysis:humanReview a analysis:Result ;
    analysis:value "Good code structure, needs documentation" ;
    analysis:metricId "code-review-quality" ;
    analysis:executionTimestamp "2024-01-15T10:30:00Z"^^xsd:dateTime ;
    analysis:measuredEntity git:commit456 ;
    analysis:wasAttributedTo analysis:developer123 ;
    analysis:wasGeneratedBy analysis:reviewExecution ;
    analysis:confidence 0.9 ;
    analysis:category "code-quality" .

analysis:reviewExecution a analysis:Execution ;
    analysis:scope "commit-review" ;
    analysis:wasAssociatedWith analysis:developer123 ;
    analysis:generated analysis:humanReview .

analysis:developer123 a analysis:HumanAgent ;
    analysis:name "Jane Developer" .

# LLM analysis example  
analysis:llmAssessment a analysis:Result ;
    analysis:value 7 ;
    analysis:metricId "maintainability-score" ;
    analysis:executionTimestamp "2024-01-15T11:45:00Z"^^xsd:dateTime ;
    analysis:measuredEntity platform:reapository789 ;
    analysis:wasAttributedTo analysis:llmAgent ;
    analysis:wasGeneratedBy analysis:llmExecution ;
    analysis:inputTokens 1500 ;
    analysis:outputTokens 50 ;
    analysis:usedConfiguration analysis:gpt4Config ;
    analysis:onScale analysis:tenPointScale .

analysis:llmExecution a analysis:Execution ;
    analysis:scope "repository-analysis" ;
    analysis:wasAssociatedWith analysis:llmAgent ;
    analysis:usesConfiguration analysis:gpt4Config .

analysis:llmAgent a analysis:AutomatedAgent ;
    analysis:name "GPT-4 Analysis Bot" ;
    analysis:attributedTo analysis:llmAssessment .

analysis:gpt4Config a analysis:LLMConfiguration ;
    analysis:model "gpt-4" ;
    analysis:temperature 0.3 ;
    analysis:maxTokens 4000 .
```

## v1 (Deprecated)

> **⚠️ Deprecated**: v1 vocabularies are no longer maintained. Please migrate to v2.

### v1 Permanent URLs (PURLs)

```turtle
@prefix git: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-git#> .
@prefix platform: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform#> .
@prefix github: <https://purl.archive.org/purl/git2rdflab/v1/git2RDFLab-platform-github#> .
```

### v1 Direct URLs

```turtle
@prefix git: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-git.ttl#> .
@prefix platform: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform.ttl#> .
@prefix github: <https://raw.githubusercontent.com/git2RDFLab/rdf-schema/main/v1/git2RDFLab-platform-github.ttl#> .
```

