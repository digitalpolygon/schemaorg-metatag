#!/bin/bash

# ###
# Deploys Drupal-Docs project Pantheon multidev and dev environments.
# ###

# Exit if anything fails
set -eo pipefail

# Cut gitignore at the cut mark.
terminus build:gitignore:cut

# Authenticate with Terminus
terminus -n auth:login --machine-token="$TERMINUS_TOKEN"

# Environment from which multidevs will be created.
CREATE_MDS_FROM="dev"
TERMINUS_ENV="dev"

if [[ "$CI_BRANCH" == "$DEVELOPMENT_BRANCH" ]]; then
  # Use develop as the environment.
  TERMINUS_ENV="develop"
fi

if [[ "$BASE_BRANCH" == "$DEVELOPMENT_BRANCH" ]]; then
  # Use develop as the environment.
  CREATE_MDS_FROM="develop"
fi

# If its a PR to development or production branch, create a multidev.
if [[ -n "$PR_NUMBER" ]] ; then
  TERMINUS_ENV="pr-${PR_NUMBER}"
fi

echo "Preparing $TERMINUS_ENV multidev from $CREATE_MDS_FROM for $TERMINUS_SITE"

set +e
  TERMINUS_ENV_EXISTS=$(terminus env:list "$TERMINUS_SITE" --field=ID | grep -w $TERMINUS_ENV)
set -e

if [[ -z "$TERMINUS_ENV_EXISTS" ]]
  then
    echo "Site $TERMINUS_SITE does not have a $TERMINUS_ENV multidev. Creating multidev from $CREATE_MDS_FROM..."
  else
    echo "Syncing documentation $TERMINUS_ENV on $TERMINUS_SITE"
    # Run The migration deploy.
    terminus drush "$TERMINUS_SITE.$TERMINUS_ENV" -- migrate:import schemaorg_metata -y;
fi
