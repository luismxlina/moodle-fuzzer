README.md
# Moodle User Enumeration Tool
This tool is designed to exploit a vulnerability in Moodle that allows for user enumeration. It works by iterating over user IDs and scraping the corresponding user data, including the user's name, email, ID, and enrolled courses.

## Installation
It is recommended to install this tool in a virtual environment to avoid conflicts with other Python packages that may be installed on your system. You can create a virtual environment and install the required dependencies as follows:

```
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
```

## Usage
The tool can be run from the command line as follows:
```
./moodle_fuzzer -s SESSION -u URL -i ID [-o OUTPUT]
```
Where:
* SESSION is the MoodleSession cookie
* URL is the base URL with 'FUZZ' in place of the ID.
* ID is the range of ID numbers (e.g., 1-50).
* OUTPUT (optional) is the name of the output CSV file. If not provided, the default is `data.csv`.

For example, to scrape user data from IDs 1-50 on the Moodle instance at `https://moodle.example.com`, you would run:
```
./moodle_fuzzer -s MoodleSession=1234567890 -u https://moodle.example.com/user/view.php?id=FUZZ -i 1-50
```

## Disclaimer
This tool is intended for educational purposes only. Always obtain proper authorization before performing any kind of security testing.The author is not responsible for any misuse of this tool.
