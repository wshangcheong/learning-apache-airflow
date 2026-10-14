1. run `uv init` in terminal when in workspace folder  
2. run `uv venv` to get virtual env running
3. run `uv pip install ...` (take sample from  "quick start" [page](https://airflow.apache.org/docs/apache-airflow/stable/start.html))
4. run `airflow version` to check that airflow was installed successfully
5. run `airflow standalone` to start the sample instance
6. open `localhost:8080` in web broswer to access airflow GUI
7. open another terminal and run `cat ~/airflow/simple_auth_manager_passwords.json.generated` to get login credentials
8. enable the `example_bash_operator` dag (search for it in DAG list)
9. run the commands below in terminal then check out for run instances in Airflow GUI under `example_bash_operator`
```
# run your first task instance
airflow tasks test example_bash_operator runme_0 2015-01-01
# run a backfill over 2 days
airflow backfill create --dag-id example_bash_operator \
    --from-date 2015-01-01 \
    --to-date 2015-01-02
``` 
10. made it here so basic airflow is working