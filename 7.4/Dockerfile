FROM php:7.4

LABEL "com.github.actions.name"="PHP Lint 7.4"
LABEL "com.github.actions.description"="Run the native PHP linter"
LABEL "com.github.actions.icon"="check"
LABEL "com.github.actions.color"="blue"

LABEL "repository"="http://github.com/dbfx/github-phplint"
LABEL "homepage"="http://github.com/actions"
LABEL "maintainer"="Dave B <dave@blakey.co>"

ADD entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/bin/sh -l /entrypoint.sh"]
