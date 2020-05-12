Jira: 
Changelog: 
Description:


---

_Jira_ field is required:
* A link to Project Quay's jira is required https://issues.redhat.com/projects/PROJQUAY/issues
* The PR title must start with the jira (eg. PROJQUAY-1234)
* Both the link and title will be automatically added if...
  * the branch is or starts with a number (eg. "1234" or "1234-my-fix")

_Changelog_ field is required:
* Put a one line description of changes, starting with change type
* Change types
  * Added for new features.
  * Changed for changes in existing functionality.
  * Deprecated for soon-to-be removed features.
  * Removed for now removed features.
  * Fixed for any bug fixes.
* See https://keepachangelog.com/en/1.0.0/ best practices

_Description_ field is optional but suggested:
* Verbose description that include details on how to test, developer context, etc.