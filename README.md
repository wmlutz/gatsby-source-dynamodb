<p align="center">
  <a href="https://www.gatsbyjs.org">
    <img alt="Gatsby" src="https://www.gatsbyjs.org/monogram.svg" width="60" />
  </a>
</p>

<h1 align="center">
  gatsby-source-dynamodb
</h1>

### How this fork improves upon the original
You may use fieldNameForNodeId field to specify an alternative Id field, if you do not have an `Id` field in your table. 


This module helps you pull your AWS dynamodb account using IAM credentials. The inspiration was designed to assist connecting private tables from AWS Amplify for public-facing sites.

To install:

```
yarn add gatsby-source-dynamodb
```

(or `npm install --save gatsby-source-dynamodb`)

Then add the config to your `gatsby-config.js`:

```js
module.exports = {
  plugins: [
    {
      resolve: 'gatsby-source-dynamodb',
      options: {
        typeName: '<INPUT_GRAPHQL_TYPE_NAME_HERE>',
        accessKeyId: '<AWS_ACCESS_KEY_ID>', 
        secretAccessKey: '<AWS_SECRET_ACCESS_KEY>',
        region: '<AWS_REGION>',
        fieldNameForNodeId: "MyIdField",
        params: {
          TableName : "<TABLE_NAME>",
          // OTHER PARAMS HERE
        }
      }
    },
  ],
};
```

## AWS CREDENTIALS

- Get your AWS Credentials for IAM user: https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/getting-your-credentials.html

- Set up permissions for your IAM user, you only need scan: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/using-identity-based-policies.html

- Use params from AWS DynamoDB Query Scan: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStarted.Js.04.html#GettingStarted.Js.04.Scan

_It is strongly recommended that credentials are stored in environment variables._

## Helpful links

- [Gatsby documentation](https://www.gatsbyjs.org/)
