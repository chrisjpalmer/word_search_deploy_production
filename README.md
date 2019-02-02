# Word Search Deploy Production
This is the word search deployment configuration for the production environment.

## Getting Started
```sh
#Get the right version
STACK_TAG = #Select an appropriate stack tag from the list below
git clone https://github.com/chrisjpalmer/word_search_deploy_production
cd word_search_deploy_production
git checkout $STACK_TAG

#Deploy the stack
eval $(docker-machine env my-machine)
docker swarm init
docker stack deploy -c word_search.yaml ws

#Test it out
IP=`docker-machine ip my-machine`
curl http://$IP/words -X
```

## Stack Tags
You can check out this repository to the stack tag which matches the versions of the `word_search_api` and `word_search_system` you want.

| stack_tag | word_search_api | word_search_system |
| --------- | --------------- | ------------------ |
| wsa-1.0.0-wss-1.0.0 | 1.0.0| 1.0.0 |