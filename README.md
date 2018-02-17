# CSIT-CPP-Dev

A light weight dev setup for Visual C++. Mainly just makes compiling, running, and zipping files easier.

## Installation:

1. Open a Terminal
2. Use the following commands to install the repo
```
git clone https://github.com/BaReinhard/CSIT-CPP-Dev
cd CSIT-CPP-Dev
# Begin Developing
```

## Usage:

1. Open a terminal in the root of the folder.
2. Run the following command to compile and run test.cpp : `npm run test`
3. Run the following command to compile and run main.cpp : `npm run test`
4. Run the following command to zip all .h and .cpp files: `npm run build`

## Configuration:

In the package.json file, you may need to make changes to the scripts.

```
"scripts": {

        // When compiling and running test or main .cpp files with include .h files,
        // simply add the header file after test.cpp or main.cpp respectively
        "test": "g++ -o test.out test.cpp -std=c++11 && ./test.out | tee  report.txt",
        "main": "g++ -o main.out main.cpp .cpp -std=c++14 && ./main.out | tee report.txt",

        // Change programmer_name_assignment.zip to something you would like your created zip file.
        "build": "rm  -rf ./*.zip && zip -r -X programmer_name_assignment.zip ./*.h ./*.cpp ./report.txt",

        // Unbuild simple unpackages any zip files into the unzipped directory
        "unbuild": "rm -rf ./unzipped/* && unzip *.zip -d ./unzipped"
    }
```

## Dependencies:

1. VS Code, although this would still work in any other text editor. VS Code seems to work better on some older mac hardware, when editors like Atom lag.
2. NodeJS and npm, both can be downloaded [here](https://nodejs.org/dist/v8.9.4/node-v8.9.4.pkg)
3. C/C++ for Visual Studio Code, can be installed via the extension manager in VS Code.
