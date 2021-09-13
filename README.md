[![Deploy Blackboard Webpages](https://github.com/uob-coms20007/webpages-src/actions/workflows/deploy_bb_webpages.yaml/badge.svg)](https://github.com/uob-coms20007/webpages-src/actions/workflows/deploy_bb_webpages.yaml)

# Webpages Source Repository

The repository contains the source code for the unit webpages that are hosted on Blackboard.  Pushing to this repository automatically invokes a Github runner to build the pages and mirror them onto the `site/` subdirectory of the course content area on Blackboard.

Do not edit the contents of the `_questions` and `_answers` directories: they are populated automatically from the [sheets-src](https://github.com/uob-coms20007/sheets-src) repository.

The detailed schedule page is generated from the [weeks](_data/weeks.yml) file.
