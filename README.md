# graphql-demo

**Setup:**
  1. cd graphql-demo
  2. cd src/backend && composer install  
  3. cd ../frontend && yarn install && yarn build  
     cd example && yarn install 
     *you can use npm instead*  
  4. cd ../.. && docker-compose up
  
**pure docker setup**  
   * *at step 2, if you don't have composer in your machine, run:*  
    docker-compose run --rm --entrypoint "composer install" backend  
   * *at step 3, if you don't have yarn or npm in your machine, run:*  
    docker-compose run --rm --entrypoint "yarn install" frontend  
    docker-compose run --rm --entrypoint "yarn build" frontend  
    docker-compose run --rm --entrypoint "bash -c 'cd example && yarn install'" frontend  
    
**Usage:**
  Voila! Go to http://localhost:8000 and test your query. Ctrl+space for autocomplete.
  
**Technical Details:**
  1. Frontend:
  * use [express](https://github.com/expressjs/express) server inside a nodejs container.
  * access in: http://localhost:8000
  * using [Graphiql](https://githuåb.com/graphql/graphiql) to test queries.
  2. Backend:
  * use [Siler](https://github.com/leocavalcante/siler/) server inside a PHP container.
  * access in: http://localhost:9000/graphql/api.php
  * using [graphql-php](https://github.com/webonyx/graphql-php/) to define graphql schema.
  
