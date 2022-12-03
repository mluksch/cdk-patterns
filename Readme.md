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
2. #### Some Cdk-Commands:
   ```
   # Creates Staging-Bucket for Deployment for the current user:
   cdk bootstrap
   
   # Displays differences in infrastructure:
   cdk diff
   
   # List all Stacks deployed with Cdk:
   cdk list
   
   # Generates Cloudformation-json-file
   cdk synth
   
   # Deploys a Stack
   cdk deploy <stack_name>
   
   # Delete a Stack:
   cdk destroy <stack_name>
   
   # Validate code:
   cdk doctor
   ```
   
#### Categories of Cdk Resources:
- Cfn Resource: 
  - Refers 1:1 to a Cfn-Resource
- Cdk Constructs: 
  - Higher level Resources with reasonable default values and easier Api
