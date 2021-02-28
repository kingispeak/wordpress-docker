# Wordpress-Docker

## Set Up WordPress

From the project directory, start your Docker containers:

```bash
# create and start containers with detached mode
$ docker-compose up -d
```

Navigate to http://localhost:8000, and you should now see website.

Navigate to http://localhost:8000/wp-json/wp/v2, and you should now see api.

## Update WordPress

```bash
# stop all contaners and remove images, volumes
docker-composer down
docker-compose pull && docker-compose up -d
```

## Maintenance

When a Docker container is stopped, it is also deleted; this is how Docker is designed to work. However, your WordPress files and data will be preserved, as the docker-compose.yml file was configured to create persistent named volumes for that data.

```bash
docker-compose down
docker-compose down --volumes
```

## Restful API

1. First set up the permanent link

2. Navigate to http://localhost:8000/wp-json/wp/v2, and you should now see api.

## Delete Volumes

```bash
# List all volumes
docker volume ls -q
```

```bash
# Remove specific volume
docker volume rm wordpress_db_data
```

```bash
# Delete all volumes
docker volume rm $(docker volume ls -q)
```

## Recommend Plugin

1. WooCommerce
2. SEYoast
3. WP API SwaggerUI
