# module-pdfbox
This repository contains the source code of the Ballerina pdfbox library package

[![Build](https://github.com/xlibb/module-pdfbox/actions/workflows/build-timestamped-master.yml/badge.svg)](https://github.com/xlibb/module-pdfbox/actions/workflows/build-timestamped-master.yml)
[![codecov](https://codecov.io/gh/xlibb/module-pdfbox/branch/main/graph/badge.svg)](https://codecov.io/gh/xlibb/module-pdfbox)
[![GitHub Last Commit](https://img.shields.io/github/last-commit/xlibb/module-pdfbox.svg)](https://github.com/xlibb/module-pdfbox/commits/main)
[![Github issues](https://img.shields.io/github/issues/xlibb/module-pdfbox/module/pdfbox.svg?label=Open%20Issues)](https://github.com/xlibb/module-pdfbox/labels/module%2Fpdfbox)
[![GraalVM Check](https://github.com/xlibb/module-pdfbox/actions/workflows/build-with-bal-test-graalvm.yml/badge.svg)](https://github.com/xlibb/module-pdfbox/actions/workflows/build-with-bal-test-graalvm.yml)

## Overview

This module offers two core APIs: one for converting PDF documents into images and another for extracting text from PDF documents, providing efficient and versatile solutions for PDF processing.

## Usage

#### Converting PDF documents into images

```ballerina
import xlibb/pdfbox;

public function main() returns error? {

    // Convert the PDF located at a file path into an array of Base64-encoded images.
    string[] base64ImagesForFilePath = check pdfbox:toImagesFromFile("C://path/to/file/myfile.pdf");

    // Convert the PDF available at a URL into an array of Base64-encoded images.
    string[] base64ImagesForURL = check pdfbox:toImagesFromURL("https://url/to/file/myfile.pdf");

    // Convert the PDF represented as a byte array into an array of Base64-encoded images.
    string[] base64ImagesForByteArr = check pdfbox:toImagesFromBytes([your, byte, array]);
}
```

#### Extracting text from PDF documents

```ballerina
import xlibb/pdfbox;

public function main() returns error? {

    // Extract text from the PDF located at a file path.
    string[] base64ImagesForFilePath = check pdfbox:toTextFromFile("C://path/to/file/myfile.pdf");

    // Extract text from the PDF available at a URL.
    string[] base64ImagesForURL = check pdfbox:toTextFromURL("https://url/to/file/myfile.pdf");

    // Extract text from the PDF represented as a byte array.
    string[] base64ImagesForByteArr = check pdfbox:toTextFromBytes([your, byte, array]);
}
```

## Examples

The `pdfbox` library provides practical examples illustrating usage in various scenarios. Explore these [examples](https://github.com/xlibb/module-pdfbox/tree/main/examples/), covering the following use cases:

1. [PDF to text](https://github.com/xlibb/module-pdfbox/tree/main/examples/pdf_to_text).

2. [PDF-JSON Converter](https://github.com/xlibb/module-pdfbox/tree/main/examples/pdf_json_converter). 

## Build from the source

### Setting up the prerequisites

1. Download and install Java SE Development Kit (JDK) version 17. You can download it from either of the following sources:

    * [Oracle JDK](https://www.oracle.com/java/technologies/downloads/)
    * [OpenJDK](https://adoptium.net/)

   > **Note:** After installation, remember to set the `JAVA_HOME` environment variable to the directory where JDK was installed.
2. Download and install [Ballerina Swan Lake](https://ballerina.io/).

3. Download and install [Docker](https://www.docker.com/get-started).

   > **Note**: Ensure that the Docker daemon is running before executing any tests.
4. Export Github Personal access token with read package permissions as follows,

    ```bash
    export packageUser=<Username>
    export packagePAT=<Personal access token>
    ```

### Build options

Execute the commands below to build from the source.

1. To build the package:

   ```bash
   ./gradlew clean build
   ```

2. To run the tests:

   ```bash
   ./gradlew clean test
   ```

3. To build the without the tests:

   ```bash
   ./gradlew clean build -x test
   ```

4. To run tests against different environments:

   ```bash
   ./gradlew clean test -Pgroups=<Comma separated groups/test cases>
   ```

5. To debug the package with a remote debugger:

   ```bash
   ./gradlew clean build -Pdebug=<port>
   ```

6. To debug with the Ballerina language:

   ```bash
   ./gradlew clean build -PbalJavaDebug=<port>
   ```

7. Publish the generated artifacts to the local Ballerina Central repository:

    ```bash
    ./gradlew clean build -PpublishToLocalCentral=true
    ```

8. Publish the generated artifacts to the Ballerina Central repository:

   ```bash
   ./gradlew clean build -PpublishToCentral=true
   ```

## Contribute to Ballerina

As an open-source project, Ballerina welcomes contributions from the community.

For more information, go to the [contribution guidelines](https://github.com/ballerina-platform/ballerina-lang/blob/master/CONTRIBUTING.md).

## Code of conduct

All the contributors are encouraged to read the [Ballerina Code of Conduct](https://ballerina.io/code-of-conduct).
