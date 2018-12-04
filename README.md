# Repro of Cloud Build error when source contains symlink
[Cloud Build](https://cloud.google.com/cloud-build/) will reproducibly fail if the source tree contains a symlink. This repo provides a reproduction...

## Working example:
`gcloud builds submit --config=cloudbuild.yaml ./nosymlink`

## Failing example:
`gcloud builds submit --config=cloudbuild.yaml ./symlink`

...the only difference between the directories is that "symlink" contains a symlink. (Which is not even used in the build FWIW.)
