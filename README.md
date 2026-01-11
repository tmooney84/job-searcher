# The Job Searcher

Welcome to the The Job Searcher!
-This is a Job Search Platform that acts to aggregate job listings from numerous companies and government organizations using scraping and API calls. It is being built with Python, Flask, Kafka, MySQL, Selenium, Docker and other technologies.


## Table of Contents
- [Usage](#usage)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Requirements](#requirements)
- [File Structure](#file-structure)
- [Installation](#installation)
- [Troubleshooting](#troubleshooting)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)

## Usage

This application is designed to assist job seekers in finding positions that better suite their skills and interests. 

## Features

# Microservices Architecture
![alt text for screen readers](/The_Job_Searcher_Architecture.jpg "The Job Searcher Architecture")

## Technologies Used
- **Python** 
- **Flask**  
- **Selenium**
- **Beautifulsoup** 
- **Kafka** 
- **MySQL** 

- **Caddy (In-Development)** 
- **Hashicorp Vault (In-Development)** 
- **Hashicorp Consul (In-Development)** 

## Requirements
In order to run this containerized application, you will need to have Docker and/or Docker Desktop installed. For more details, navigate your web browser to https://docs.docker.com/engine/install for more details.

## File Structure
```text
The-Job-Board 2/
├── consumer_service/
│   ├── Dockerfile
│   ├── consumer_main.py
│   ├── consumer_service.py
│   └── requirements.txt
├── frontend/
│   ├── Dockerfile
│   ├── templates/
│   │   └── detail_page.html
│   │   └── index.html
│   ├── app.py
│   ├── Dockerfile
│   ├── models.py
│   └── requirements.txt
├── models/
│   ├── __init__.py
│   ├── init.sql
│   ├── models.py
├── scraper_orchestrator/
│   ├── Dockerfile
│   ├── publisher_service.py
│   ├── publisher_main.py
│   ├── requirements.txt
│   ├── scrapers/
│   │   └── ibm_scraper.py
│   │   └── site1_scraper.py
│   │   └── site2_scraper.py
│   └── requirements.txt
├── clear_kafka_logs.sh
├── docker-compose.yml
├── docker_build_and_spin_up.sh
├── docker_stop_and_clean.sh
```

## Installation

To run this website locally, follow these steps:

1. Clone the repository:

    using sh:
    ```sh
    git clone git@github.com:tmooney84/job-searcher.git
    ```

    using https:
    ```sh
    git clone https://github.com/tmooney84/job-searcher.git
    ```

2. Navigate to the project directory:
    ```sh
    cd "The-Job-Board 2"
    ```

3. To build and start services:

    ```sh
    $ ./docker_build_and_spin_up.sh
    ```

4. Open `localhost:6300` in your preferred web browser to view the front end of the application.

5. To close the application and remove old containers run:
    ```sh
    ./docker_stop_and_clean.sh
    ```

6. Enjoy!

## Troubleshooting

Navigate to ```localhost:9000``` to access the KAFDROP GUI interface to see if the sql_queue topic is set up correctly. It should include a topic named sql_queue that has 3 partitions and a replication factor of 3. If missing add it manually through the KAFDROP GUI by pressing the "+New" button and filling out the topic information.

## Future Improvements
- Complete the authentication logic including OAuth2, authorization, 2-Factor Authentication security, secrets management (Hashicorp Vault), service discovery/service mesh (Hashicorp Consul)
- Build out Model Context Protocol Server, Prompting, Tools and Resources
- Refine the job search functionality using prompting and MCP
- Create an automated resume editor using MCP 


## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.

## License

Copyright (c) 2026 Trevor Mooney and Anthony Brown

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


---





