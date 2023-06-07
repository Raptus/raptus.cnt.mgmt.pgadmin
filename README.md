# pgAdmin4
Since phppgadmin is not maintained anymore, use the [dpage/pgadmin4]("https://hub.docker.com/r/dpage/pgadmin4/") docker image, for deploying a management instance, when using PostgreSQL Database Instances.

# Deployment
You can add Docker Hub as a Registry source and deploy the container to Azure with no effort. I would recommend to disable Continuous deployment, for stability reasons.

# Configuration


## Application Settings

The following ENVs are recommended to use:

* PGADMIN_DEFAULT_EMAIL = admin e-mail
* PGADMIN_DEFAULT_PASSWORD = savepw
* PGADMIN_CONFIG_ENHANCED_COOKIE_PROTECTION = False
* PGADMIN_CONFIG_DATA_DIR = '/pgadmindata'
  * The '' are important when setting the value in the Azure Portal

## Path mappings

The recommendation ist, to store the configdata outside the container. A standard storage account with Azure Files activated would be sufficent.

* Storage type: Azure Files
* Mount path: /pgadmindata
  * like the path you defined in the application settings


