# AWS CDK-Patterns 
1. #### Pass Parameters from CLI to Stack:
   - In CLI:
       ```shell
       npx cdk deploy --context environment=staging
       ```
   - In Stack:
       ```typescript
       const env = this.node.tryGetContext("environment");
       ...
       const restApi = new cdk.aws_apigateway.RestApi(this, "restApi1", {
             restApiName: "rest",
             deployOptions: {
               stageName: env,
             },
       });
       ```