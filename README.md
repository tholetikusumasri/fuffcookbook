# fuffcookbook
Description fuff is a powerful and flexible tool designed for fuzzing HTTP endpoints, particularly useful for web application security testing. It allows security professionals to discover hidden files, directories, parameters, and other vulnerabilities by sending numerous HTTP requests with various inputs. With its highly customizable and performant nature, fuff stands out as an essential tool in a security analyst's toolkit. Installation To install fuff, use the following command: go install github.com/ffuf/ffuf/v2@latest Ensure that Go is installed and properly configured on your system. (Or) We can simply use command : "apt-get install fuff"

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/8d167f64-1686-41eb-a6ac-36c5f293d202)

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/591e0fa8-3da2-43c4-8aea-01b962b512a0)

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/187c10c3-4b8a-47a5-89a8-0b71114e0421)

Basic Usage : 1.Fuzzing Directories To fuzz directories on a website: "fuff -u https://example.com/FUZZ -w wordlist.txt" • -u: URL with the placeholder FUZZ where the payload will be inserted. • -w: Path to the wordlist file containing potential directory names.

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/182ed9e0-ed3e-4ee6-a1d0-1b1422be29b5)

2.Fuzzing GET Parameters To fuzz GET parameters: "fuff -u https://example.com/page?FUZZ=value -w wordlist.txt"

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/39a46603-edd2-4e69-a9f5-ed50f11d3040)

3.Fuzzing POST Data To fuzz POST data: "fuff -u https://example.com/login -w wordlist.txt -X POST -d 'username=admin&password=FUZZ' " • -X POST: Specifies the HTTP method to use (POST in this case). • -d: Data to be sent in the body of the POST request.

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/3f546050-f052-4fd9-ba70-e7cd7bb76569)

4.Multi-Wordlist Fuzzing To use multiple wordlists simultaneously: "fuff -u https://example.com/FUZZ/FIZZ -w wordlist1.txt -w wordlist2.txt"

5.Using Filters To filter out results based on response status codes, sizes, or words: • Filter by status code: fuff -u https://example.com/FUZZ -w wordlist.txt -fc 404

• Filter by response size: fuff -u https://example.com/FUZZ -w wordlist.txt -fs 1234

• Filter by number of words in the response: fuff -u https://example.com/FUZZ -w wordlist.txt -fw 100

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/4be7d15e-75f5-4f79-a454-b46b49a464e0)

6.Recursion To recursively fuzz discovered directories: fuff -u https://example.com/FUZZ -w wordlist.txt -recursion

![image](https://github.com/tholetikusumasri/fuffcookbook/assets/121847328/67af3ea4-28d6-4564-a789-1f1d262102b0)

7.Specifying Headers To specify custom headers: fuff -u https://example.com/FUZZ -w wordlist.txt -H 'Authorization: Bearer token' -H 'Custom-Header: value'

8.Output Options To save the output in various formats: • JSON: fuff -u https://example.com/FUZZ -w wordlist.txt -o output.json -of json

• CSV: fuff -u https://example.com/FUZZ -w wordlist.txt -o output.csv -of csv

9.Speed and Timing To control the speed and timing of requests: • Number of concurrent requests: fuff -u https://example.com/FUZZ -w wordlist.txt -t 50

• Rate limiting (requests per second): fuff -u https://example.com/FUZZ -w wordlist.txt -rate 100
