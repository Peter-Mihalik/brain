
2025-07-02 18:32
Tags: #cpp
Status:

---
# files
- handling files is provided by [[ifstream]], [[ofstream]], [[fstream]]
- to open a file you have to instantiate file stream ofject
- files closes automatically when it goes out of [[scope]] but it is good practice to close to free resources and avoid [[memory_leak]]
- to manage filesystems use [[filesystem]]
```cpp
#incluse <fstream>

// Writing to a file
std::ofstream outputFile {"Test.txt"}; //open file for output
outputFile << "Text to write"; //write to a file
if (!outputFile) { // Check whether opening was successfull
	std::cerr << "Failed to open file";
}

// Reading a file
std::ifstream inputFile {"InputFile.txt"}; // open for reading
std::string str{};
// inputFile >> str; can be used for reading words
while(std::getline(inputFile, str)) { // use get line for reading a line
	std::cout << str << std::endl; 
}

// Closing a file
inputFile.close();
```
## Modes
![[file_modes.jpg]]
```
std::ofstream f {"fileName.txt", std::ios::app};
```

---
## References
[Learn Cpp](https://www.learncpp.com/cpp-tutorial/basic-file-io/)
[Geeks](https://www.geeksforgeeks.org/cpp/file-handling-c-classes/)


