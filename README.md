# 8base Beginner Walkthrough

## Prerequisite
* <a href="https://nodejs.org/en/">Node.js</a>
* <a href="https://yarnpkg.com/lang/en/docs/install/">yarn</a>
* Yarn: `yarn global add cross-env`

## Data Model
1. Login to https://app.8base.com
2. Create a `Properties` table with the following fields:
* `Title: Text` 
* `Description: Text`
* `Pictures: File (Allow Multiple)`
* `Bedrooms: Number`
* `Sq Footage: Number`
* `Bathrooms: Number`
* `Garage: Switch`
* `Pool: Switch`

3. Click on "Data" and manually add a few Properties.
4. Check that you can query your data using "API Explorer"

## React

1. Clone repo: `git clone https://github.com/8base/hackathon-starter-kit.git`
2. Go to the client directory `cd client`;
3. Edit `src/routes/properties/PropertiesTable.js` and complete the `PROPERTIES_LIST_QUERY` GraphQL query:
```
const PROPERTIES_LIST_QUERY = gql`
  query PropertiesList {
    propertiesList {      
      items {
        id
        createdAt
        updatedAt
        pictures {
          items {
            id
            downloadUrl
            shareUrl
          }
        }
        bedrooms
        title
        description
        sqFootage
        bathrooms
        garage
        pool
      }
    }
  }
`;
```
4. Edit `src/routes/properties/PropertyCreateDialog.js` and complete the `PROPERTY_CREATE_MUTATION` GraphQL mutation:
```
const PROPERTY_CREATE_MUTATION = gql`
  mutation PropertyCreate($data: PropertyCreateInput!) {
    propertyCreate(data: $data) {
      id
    }
  }
`;
```
5. Install dependencies `yarn`;
6. Get 8base API endpoint for your account;
7. Start app via `cross-env REACT_APP_8BASE_API_ENDPOINT=!YOUR_ENDPOINT! npm start`;

## Server Logic

1. Install 8base CLI: `yarn global add 8base`
2. Login using CLI `8base login`;
3. Go to the server directory `cd ../server`
4. Take a look at `8base.yml` and `src/propertyShare.js`
5. Deploy server logic using `8base deploy`
6. Test the feature in the app
