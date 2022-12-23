API DESIGN

StarWarsAPI
Context /swapi
Version 1.0.0
Endpoints http://localhost:8080/graphql
Schema : https://apim.docs.wso2.com/en/4.0.0/assets/attachments/learn/schema_graphql.graphql

BACKEND : 
PROXY : 
TEST PROXY : curl -kvx http://10.56.254.13:3128 https://registry.npmjs.org
export https_proxy=http://10.56.254.13:3128
export http_proxy=http://10.56.254.13:3128

git clone https://github.com/wso2/samples-apim
OK
mv samples-apim graphql
cd graphiql/graphql-backend

#npm init
#npm install
	
wget https://deb.nodesource.com/setup_10.x

mv setup_10.x nodejs_setup_10.x.sh

vi nodejs_setup_10.x.sh

export http_proxy="http://10.56.254.13:3128"
export https_proxy="http://10.56.254.13:3128"

curl -x 10.56.254.13:3128
curl -x 10.56.254.13:3128

apt update
sh nodejs_setup_10.x.sh

node -v
<< v10.24.1

npm -v
<< 6.14.12

# RESTAURE node
wget https://nodejs.org/download/release/v10.24.1/node-v10.24.1-linux-x64.tar.gz

tar -C /usr/local --strip-components 1 -xzf node-v10.24.1-linux-x64.tar.gz


# extra modules
npm install nodemon --save-dev

npm start
lsof -i -P -n | grep LISTEN
#killall node
endpoint : http://localhost:8080/graphql
VM DD : 10.246.71.28

#CREATE & PUBLISH
https://pub-wso2v4-poc.devops.iaas.cagip.gca/publisher

Name : StarWarsAPI
Context : /swapi
Version : 1.0.0
Endpoint : http://localhost:8080/graphql

#TEST
https://gw-wso2v4-poc.devops.iaas.cagip.gca:8243/swapi/1.0.0

# TO WSO2 GW
curl -k 'https://gw-wso2v4-poc.devops.iaas.cagip.gca:8243/swapi/1.0.0' -X POST -H 'content-type: application/json' --data '{"query": "{ allHumans(first: 1) }" }'


#TO KONG GW
curl -k 'https://kong-cagip-dp.devops-hors-prod.caas.cagip.group.gca/graphql' -X POST -H 'content-type: application/json' --data '{ "query": "{ allHumans(first: 10) { id } }" }'
OK

curl -k 'https://10.245.144.1/graphql' -X POST -H 'content-type: application/json' --data '{ "query": "{ allHumans(first: 10) { id } }" }'
curl -k 'https://dd063inf0076.devops.iaas.cagip.gca/graphql' -X POST -H 'content-type: application/json' --data '{ "query": "{ allHumans(first: 10) { id } }" }'
curl -k 'https://localhost/graphql' -X POST -H 'content-type: application/json' --data '{ "query": "{ allHumans(first: 10) { id } }" }'

query{
    human(id:1000){
        id
        name
    }
    droid(id:2000){
        name
        friends{
            name
            appearsIn
        }
    }
}