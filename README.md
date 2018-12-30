# CF Provider Bugs

A support ticket has been filed containing a pointer to this repo.

To validate this bug, please:

- clone this repo
- change to the directory specified in the support ticket
- run "make test"
- observe failure

Please fix the Cloud Foundry instance's bug, and then:

- change to the directory specified in the support ticket
- run "make test"
- observe success
- update the support ticket with the output of the successful test run
