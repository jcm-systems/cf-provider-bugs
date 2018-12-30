LOGFILE=cf-trace-$(shell echo $$$$).log
APPNAME=multi-buildpack-404
ifndef VERBOSE
MAKEFLAGS += --silent
endif

default:
	echo "Please run 'make test' whilst logged in as a CF user to validate this bug."
	echo "Run 'make clean' to clean up afterwards."

test: logged-in show-settings
	echo
	echo "*** CF API request/response logging into $(LOGFILE) ***"
	echo
	CF_TRACE=$(LOGFILE) cf push $(APPNAME) -f manifest.yml

logged-in:
	cf target >/dev/null 2>/dev/null || \
	echo "We're not logged in to a Cloud Foundry environment. Please log in."

show-settings:
	echo "*** OS version ***"
	uname -a
	echo "*** CF version ***"
	cf version
	echo "*** CF API ***"
	cf target

clean: logged-in
	cf delete -f -r $(APPNAME)
