# Laravel-Docker-Boilerplate

This boiler plate can be used to setup Laravel project using Docker without any local configurations .i.e PHP, Nginx or Postgres installed. This compose will set up
six containers mandatory for any Laravel project. i.e PHP, Nginx, MySQL or PostgreSQL, Composer, Artisan and NPM. To use this boilerplate, clone it using:

    git clone git@github.com:sharryy/Laravel-Docker-Boilerplate.git
    
Remove the `index.php` file inside `src/` directory since Laravel project will be created inside that directory. Add credentials of database in `database.env` file and 
corresponding database in `docker-compose.yml` (default is MySQL). Then run following command to build composer service:

    docker-compose build composer -d
    
Use following command to create laravel  project inside `src/` directory.

    docker-compose run composer create-project laravel/laravel .

This will create Laravel project inside `src/` directory. Then run `docker-compose up --build -d` to spin up Nginx and Database containers.

Visit `http://localhost:8000` in your browser.

> **_NOTE:_** If you are encountering any file permission problems, then change the default user and group(which is Laravel in this case) for PHP, Nginx and Composer Dockerfile according to your File System. For MAC 
users, there is no need of it since it creates virtualization layer between file systems. However, for Windows, Linux or WSL2 you need to configure user and groups for
proper working.

| :exclamation:  This dockerized setup should be used for development only and any production use is discouraged. |
|-----------------------------------------|
