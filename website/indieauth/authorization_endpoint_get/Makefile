build-AuthorizationEndpointGet:
	cp *.py $(ARTIFACTS_DIR)
	cp requirements.txt $(ARTIFACTS_DIR)
	cp get.html $(ARTIFACTS_DIR)
	python3.8 -m pip install --platform linux_x86_64 --no-deps -r requirements.txt -t $(ARTIFACTS_DIR)
	rm -rf $(ARTIFACTS_DIR)/bin
