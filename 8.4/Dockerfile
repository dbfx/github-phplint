FROM php:8.4

LABEL "com.github.actions.name"="PHP Lint 8.4"
LABEL "com.github.actions.description"="Run the native PHP linter"
LABEL "com.github.actions.icon"="check"
LABEL "com.github.actions.color"="blue"

LABEL "repository"="http://github.com/dbfx/github-phplint"
LABEL "homepage"="http://github.com/actions"
LABEL "maintainer"="Dave B <dave@blakey.co>"

COPY entrypoint.sh /entrypoint.sh
RUN chmod 555 /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
