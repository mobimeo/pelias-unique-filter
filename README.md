# Pelias Unique Token Filter 

Adapted from the official Elasticsearch [Unique Token Filter](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-unique-tokenfilter.html).

Currently, this plugin exists to provide this [fix](https://github.com/elastic/elasticsearch/pull/35420) in ES 6.6.2. 

## ElasticSearch version support

This plugin is compatible with ES 6.6.2.

## Build

To build .zip or .jar for this plugin, run following command and you should see generated files in `/target`.

    mvn clean install

## Install

To install on your current ES node, use the plugin binary provided in the Elasticsearch bin folder.

    sudo bin/elasticsearch-plugin install https://github.com/moovel/pelias-unique-filter/releases/download/v1.0.0/unique-filter-1.0.0.zip
    
## Test

    mvn test

## Release

First add the following settings to `settings.xml`:

```
<servers>
    <server>
        <id>github</id>
        <username>GITHUB_USERNAME</username>
        <password>GITHUB_TOKEN</password>
    </server>
</servers>
```

You can get a Github token by following the [docs](https://help.github.com/articles/authorizing-a-personal-access-token-for-use-with-a-saml-single-sign-on-organization/).

Then run:
    
    mvn clean package 

    mvn github-release:release

**The above should be moved to a CI build.**

## Usage

The plugin provides a token filter of type `pelias_unique` which has the same usage as the [Unique Token Filter](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-unique-tokenfilter.html) provided by Elasticsearch.
