# arduino
Template for Arduino development

## Table of contents

<!-- toc -->

- [Contents](#Contents)
- [Usage](#usage)
- [Contributing](#contributing)

<!-- tocstop -->

## Contents

This template includes a Docker file to assist with local development and for CI building.
The Docker image created from the file using the GitHub workflow 'docker-build-test-publish'

The Docker Image is bukt on Ubuntu and contains the following tools:
        zip 
        curl 
        wget 
        unzip
        make
        git
        doxygen
        graphviz
        gcc
        ninja
        python3
        cmake
        ruby
        ceedling
        astyle
        arduino-cli
        arduino-lint
        arduino-fwuploader

## Usage

# When using this for a new project
The DockerHub repo must exist
The DockerHub repo must be public not private
The DockerHub user and personal access token must be added as secrets to the GitHub repo using the names; DOCKERHUB_USER and DOCKERHUB_PAT

The minimal workflow to run the default checks on the projects in the repository:

## Contributing

To report bugs or make feature requests, please submit an issue: https://github.com/dermot-murphy/arduino/issues

Pull requests are welcome! Please see the [contribution guidelines](.github/CONTRIBUTING.md) for information.