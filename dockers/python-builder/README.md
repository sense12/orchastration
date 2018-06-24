# Build instructions

docker build -t sense12/python-builder:0.1.0-alpha1 .


# Details

the makefile is a standardized makefile for python projects
The docker should only contain dependencies for the sequence of install/prepare, test build and verify stages

# Example usage in Concourse

```
---
platform: linux

image_resource:
  type: docker-image
  source: {repository: sense12/python-builder}

run:
  path: sh
  args:
  - -exc
  - |
    alias make="make -f /files/Makefile"
    ls -l
    make build
```
