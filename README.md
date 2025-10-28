# ETL-E-Commerce-Simulation
This is a project I work on to create a simulated e-commerce website with fake customer, order, order line, and product information. To use this project, you would need to have mySQL installed, Apache Airflow using Docker Desktop, and VSCode (or any Python IDE).

Instructions:
Hello! This is a simulated e-commerce project where I was able to simulate data engineering principles for a simulated e-commerce datastream. I was able to extract, transform, and load the data into a data warehouse (mySQL). I utilized Windows Task Scheduler to run the official "simulate_ecommerce.py" file every two weeks. 
**Note - If you want, you could just run the code once, and it would create fake data to utilize.**

I have environment variables that I have used to name mySQL database, user, and password inside the "employees-airflow-docker" folder. This can be changed based on what you want to define your mySQL credentials to be. In addition, for the currency conversion in the transformation stage, I utilized "https://app.exchangerate-api.com/sign-in" website, and you would need an API key. In the environment file, replace "EXCHANGE_RATE_API_KEY" with your own unique id once you create an account. The ecommerce etl_logic files will be inside the "employees-airflow-docker" file, and inside "dags", then "ecommerce_etl" folder. And the new and processed csv files will be loaded into the "data" folder. 

To check and see if data loads properly into mySQL database, you would need to make sure that you have Docker Airflow up and running, so that way data can be ETL into mySQL.
Next, in VSCode, you would need to run in terminal:
docker compose -f docker-compose.mysql.yaml run airflow-webserver airflow db init
docker compose -f docker-compose.mysql.yaml up -d
Then, you would go to localhost:8080, until airflow loads. You would type username and password for your Apache airflow. (might have to create it in VSCode terminal first)
You should see the ecommerce dag.
Check to see if it is loading into mySQL properly (should be green circles with a number in the middle, when you click on dag)

If it was successful, you can login to mySQL with a new connection utilizing 3307 as the port number, and then your username and password that you used in the environment folder. 

And VIOLA! You should see the simulation of an ETL e-commerce datastream!
