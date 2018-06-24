
.PHONY: build
build: venv release dist
	@echo "Done"

.PHONY: dist
dist: clean
	python setup.py sdist

.PHONY: release
release: clean
	./bin/version bump --increment minor

.PHONY: clean
clean:
	rm -rf dist/

.PHONY: venv
venv:
	python3 -m venv ./venv
	pip install -r requirements.txt
