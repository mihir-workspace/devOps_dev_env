# Dev-Env container

*This is Docker contianer use for creating the dev enviroment to launch the Jupyter-Lab*

Add the packages name that need to pre-install in `requirement.txt` file.

Container follow this file structure. 
```
home/
    |
    |- data/
    |- notebooks/
    |- requirement.txt
    |- README.md
```
To build the contianer 
```shell
cd Dev-Env
docker build -t dev_env_notebook .
```

To run the container
```shell
docker run-p 7000:7000 dev_env_notebook
```

Optionaly you can volumn mount the data folder and name the container. (*project_name*)

```shell
docker run --name project_name_data -v <local_path>/data:/home/data -p 7000:7000 dev_env_notebook
```

By deafult it use 7000 port to launch the notebook use can customize it to other example(8090)
```shell
docker run --name project_name  -p 8090:7000 dev_env_notebook
```




