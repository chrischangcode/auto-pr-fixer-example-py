# auto-pr-fixer-example-py

Demo repo for [auto-pr-fixer](https://github.com/chrischangcode/auto-pr-fixer).

## Scenario

A CVE fix PR bumps `flask` from 2.3.0 to 3.0.0, but leaves `werkzeug` pinned
at 2.3.0. Flask 3.0 requires `werkzeug>=3.0.0`, so `pip install` fails with a
dependency conflict. auto-pr-fixer detects the CI failure, calls the GitHub
Models API, and commits a fix (bumping werkzeug to 3.0.0).
