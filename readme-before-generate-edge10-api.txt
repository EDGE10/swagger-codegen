- download swagger json file
- replace all "$ref":"#/definitions/System.Object" with "type":"object"  (including quotes)
- remove:
  "System.Object":{
	 "type":"object",
	 "properties":{

	 }
  },
- replace all \r\n with empty string	  

- create config file with following content:
{
  "modelPackage":"Edge10.Api.Client.Model",
  "apiPackage":"Edge10.Api.Client.Api"
}

- run code gen 
java -jar modules/swagger-codegen-cli/target/swagger-codegen-cli.jar generate -i d:\edge10.json -c d:\config.json -l csharp -o d:\generated-api