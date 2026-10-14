ref [link](https://airflow.apache.org/docs/apache-airflow/stable/tutorial/fundamentals.html)

**side note:** don't run `uv sync` unless `apache-airflow` has been added to pyproject.toml using `uv add apache-airflow`

learned about main components of a dag:
- the dag itself, comprises of tasks/operators
- as of now, not sure if a task can be multiple operators but I learned to declare an operator as a task
- there are other operators available besides BashOperator
- default arguments for dag
- define dependencies using "<<", ">>", "[]"

**task IDs have to be defined**

tasks run through args by precedence of:  
arguments passed in > default arguments > operator default values (if any)

to test the pipeline, since I created my own .py file, I also had to repoint the `AIRFLOW__CORE__DAGS_FOLDER` var (found in airflow.cfg) to my working directory. One would do so by:  
1. run `export AIRFLOW__CORE__DAGS_FOLDER="{absolute path of the folder that holds your dag file}"` in the terminal
2. run `echo $AIRFLOW__CORE__DAGS_FOLDER` to check if the repointing is done

follow through with the steps from [hereon](https://airflow.apache.org/docs/apache-airflow/stable/tutorial/fundamentals.html#command-line-metadata-validation) and we're good.