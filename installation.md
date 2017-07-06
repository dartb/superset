Manual Rancher installation steps:
1. Pull down code from https://github.com/dartb/superset
2. In Rancher, click the ‘Add Stack’ button
3. Name the application, paste in the docker-compose.yml and rancher-compose.yml text from the github repo, and click ‘Create’. Note, you will want to make sure that port 8088 is available in your Rancher environment. If it is not, you can change the port to another option - example: 8123:8088. You will also want to add your mapbox API key if you have one in place of ‘${MAPBOX_API_KEY}‘.
4. Once the application stack has started and all containers are running, click on the superset container link.
5. In that container, click on the three vertical dots button and select ‘Execute Shell’. Note: you want to make sure to click the three vertical dots button to the right of the container and not in the upper right.
6. In the shell you will want to enter the following commands in order (the first one will ask you to provide user/pass info):

	```fabmanager create-admin --app superset```

	```superset db upgrade```

	```superset load_examples```

	```superset init```


7. When that is completed successfully, close the shell window, return to the Rancher stack view and click on the port link (default is 8088) in the superset container row. This will launch the application. Enter in the user/pass information you added in step 6 and you should be good to go.
