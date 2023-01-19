# EXOGEM

Imagine you have your current folder to generate the three applications (client, server, exogem server) in. All the current distribution of EXOGEM is in ../current

To generate the exogem server, you have to do:
```
java -jar ../current/openapi-generator-cli.jar generate --generator-name nodejs-express-server --input-spec ../current/openapis/exogemserver.yaml --output exogemServer
cp ../current/DefaultService.js exogemServer/services/
```

To generate the server, you have to do:

```
java -jar ../current/openapi-generator-cli.jar generate --generator-name nodejs-express-server --input-spec ../current/openapis/openapi.yaml --output server --template-dir ../current/templates/server/
cp -a ../current/uppaal server/
cp ../current/ImageService.js server/services/
```

For the client:
```
java -jar ../current/openapi-generator-cli.jar generate --generator-name javascript --input-spec ../current/openapis/openapi.yaml --output client --template-dir ../current/templates/client/
cp ../current/justClient/* ./client/
```
