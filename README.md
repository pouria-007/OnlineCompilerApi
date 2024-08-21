# Online Compiler API with Flask<br><br>

This project is an online compiler API built using Flask. It allows you to send code in various programming languages via a POST request, compile and execute the code, and return the output. The API currently supports Python, C, C++, and Java.<br><br>

## Features<br><br>
- **Multi-language Support:** Compile and run code in Python, C, C++, and Java.<br>
- **Dynamic File Generation:** Generates temporary files for code, input, and compilation on the fly.<br>
- **Sandboxed Execution:** Uses multiprocessing to limit the execution time of the code, preventing infinite loops and long-running processes.<br>
- **Clean-up Mechanism:** Automatically deletes generated files after execution to keep the environment clean.<br><br>

## Installation<br><br>

Clone the repository and navigate to the project directory:<br><br>
<code>git clone https://github.com/yourusername/online-compiler-api.git</code><br>
<code>cd online-compiler-api</code><br><br>

Install the required dependencies:<br><br>
<code>pip install flask flask_cors</code><br><br>

## Usage<br><br>

Start the Flask server:<br><br>
<code>python app.py</code><br><br>

The API will be available at `http://localhost:5000/`. You can send a POST request to this endpoint with the following parameters:<br><br>

- `code`: The code you want to compile and run.<br>
- `lang`: The programming language of the code (`py` for Python, `c` for C, `cpp` for C++, `java` for Java).<br>
- `inpt`: The input to be provided to the program during execution.<br><br>

### Example POST Request<br><br>

Here's an example of how to send a POST request to the API using `curl`:<br><br>
<code>
curl -X POST http://localhost:5000/ -F 'code=print("Hello, World!")' -F 'lang=py' -F 'inpt='
</code><br><br>

## How It Works<br><br>

1. **Random Name Generation:** A random name is generated for each code submission to avoid conflicts.<br>
2. **File Creation:** The code and input are saved as temporary files.<br>
3. **Compilation and Execution:** A Python script is dynamically generated to compile and execute the code, capturing the output.<br>
4. **Output Retrieval:** The output of the program is returned as the API response.<br>
5. **Clean-up:** All generated files are deleted after execution.<br><br>

## Contributing<br><br>

If you'd like to contribute to this project, please fork the repository and submit a pull request. Contributions are welcome!<br><br>

## License<br><br>

This project is licensed under the MIT License.
