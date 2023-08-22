# Ocean Data Management System v0.1
This is an API documentation of a third party ocean data management system. This system provides a schema for storing oceanogrpahic datasets such as Vector, Raster, Pointcloud, Lidar, Drone, Satellite Imagery, etc.

#### Models
- Member
- Contact
- Country
- DataType
- Spatial Extent
- URL
- License
- Organization
- Project
- Spatial Projection
- Tag
- Topic
- Metadata

#### Members Model
- It is a secret to create a user with administrator previledges. A default admin user has been created to be used for testing purposes `username: admin` `password: S1mpl3x`
- To create a normal user
post`
  {
    "first_name": "divesh",
    "last_name":"anuj",
    "username": "user",
    "email": "user@spc.int",
    "password": "admin",
    "roles": ["registered"],
    "organization_id":"SPC",
    "country_id":"FJ"
}`
- To Sign in https://opmdata.gem.spc.int/api/auth/signin post
`{
    "username":"admin",
    "password":"admin"
}`
- To refresh the token https://opmdata.gem.spc.int/api/auth/refreshtoken 
`{
    "refreshToken":"2e4a44e0-0f34-4c89-9d41-f9908c9f6f7f"
}`
- To access protected pages, pass `x-access-token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6NCwiaWF0IjoxNjkyNjU4NTczLCJleHAiOjE2OTI2NTg2MzN9.9M1sd0PmQKhp4pOlvjF9S9lK-9e2dc91ktQhMiwm4Vo` as header with the json request.
- To reset password: https://opmdata.gem.spc.int/api/auth/forgotPassword 
`{
    "email":"divesha@spc.int"
}`

Note: JWT expires in 1 hour and Refresh Token expires in 24 hours. Incase access token has been expired, post refresh token to get a new access token

#### Contact Model
- List all contacts: https://opmdata.gem.spc.int/api/contacts
- Add contacts: https://opmdata.gem.spc.int/api/contact/add
  post `{
    "first_name":"FJX",
    "last_name":"New",
    "email":"stan@spc.int",
    "designation":"hello"
}` required `x-access-token`
- Find contact by pk https://opmdata.gem.spc.int/api/contact/findById 
`{
    "email":"divesha@spc.int"
}`
- Update a contact by pk https://opmdata.gem.spc.int/api/contact/update 
post body `{
    "email":"divesha@spc.int",
    "first_name":"xxxxx"
}`
required `x-access-token`
- Delete contact by email: https://opmdata.gem.spc.int/api/contact/delete 
`{
    "email":"divesha@spc.int"
}`
required `x-access-token`

#### Country Model
- List All countries https://opmdata.gem.spc.int/api/countries
- Add a country: https://opmdata.gem.spc.int/api/country/add
  post: `{
    "short_name":"SM",
    "name":"Solomons"
}`
required `x-access-token`
- Find country by short_name https://opmdata.gem.spc.int/api/country/findById
  ` {
    "short_name":"SM"
}`
- update country by short_name: https://opmdata.gem.spc.int/api/country/update
  `{
    "short_name":"SM",
    "name":"xxxxx"
}`
required `x-access-token`
- Delete country by short_name https://opmdata.gem.spc.int/api/country/delete
  `{
    "short_name":"SM"
}`
required `x-access-token`

#### DataType Model
- List All data types https://opmdata.gem.spc.int/api/datatypes
- Add a datatype: https://opmdata.gem.spc.int/api/datatype/add
  post: `{
    "name":"Point"
}`
required `x-access-token`
- Find datatype by id https://opmdata.gem.spc.int/api/datatype/findById
  ` {
    "id":"3"
}`
- update datatype by id: https://opmdata.gem.spc.int/api/datatype/update
  `{
    "id":"3",
    "name":"xxxxx"
}`
required `x-access-token`
- Delete datatype by short_name https://opmdata.gem.spc.int/api/datatype/delete
  `{
    "id":"3"
}`
required `x-access-token`

#### Extent Model
- List All Extents https://opmdata.gem.spc.int/api/defineextents
- Add a extent: https://opmdata.gem.spc.int/api/defineextent/add
  post: `{
    "name":"dummy"
}`
required `x-access-token`
- Find extent by name https://opmdata.gem.spc.int/api/defineextent/findById
  ` {
    "name":"dummy"
}`
- update extent by name: https://opmdata.gem.spc.int/api/defineextent/update
  `{
    "name_old":"dummy",
    "name_new":"xxxx"
}`
required `x-access-token`
- Delete extent by name https://opmdata.gem.spc.int/api/defineextent/delete
  `{
    "name":"xxxx"
}`
required `x-access-token`

#### URL Model
- List All URLs https://opmdata.gem.spc.int/api/defineurls
- Add a URL: https://opmdata.gem.spc.int/api/defineurl/add
  post: `{
    "name":"dummy"
}`
required `x-access-token`
- Find URL by name https://opmdata.gem.spc.int/api/defineurl/findById
  ` {
    "name":"dummy"
}`
- update URL by name: https://opmdata.gem.spc.int/api/defineurl/update
  `{
    "name_old":"dummy",
    "name_new":"xxxx"
}`
required `x-access-token`
- Delete URL by name https://opmdata.gem.spc.int/api/defineurl/delete
  `{
    "name":"xxxx"
}`
required `x-access-token`

#### License Model
- List All license https://opmdata.gem.spc.int/api/licenses
- Add a license: https://opmdata.gem.spc.int/api/license/add
  post: `{
    "title":"dummy",
    "url":"dummy"
}`
required `x-access-token`
- Find license by id https://opmdata.gem.spc.int/api/license/findById
  ` {
    "id":"2"
}`
- update license by id: https://opmdata.gem.spc.int/api/license/update
  `{
    "id":"2",
    "title":"john",
    "url":"doe"
}`
required `x-access-token`
- Delete license by id https://opmdata.gem.spc.int/api/license/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Organization Model
- List All organizations https://opmdata.gem.spc.int/api/organizations
- Add a organization: https://opmdata.gem.spc.int/api/organization/add
  post: `{
    "short_name":"dummy",
    "name":"dummy"
}`
required `x-access-token`
- Find organization by name https://opmdata.gem.spc.int/api/organization/findById
  ` {
    "short_name":"dummy"
}`
- update organization by name: https://opmdata.gem.spc.int/api/organization/update
  `{
    "name_short_name_old":"dummy",
    "name_short_name_new":"xxxx",
    "name":"hello"
}`
required `x-access-token`
- Delete organization by name https://opmdata.gem.spc.int/api/organization/delete
  `{
    "short_name":"xxxx"
}`
required `x-access-token`

#### Project Model
- List All project https://opmdata.gem.spc.int/api/projects
- Add a project: https://opmdata.gem.spc.int/api/project/add
  post: `{
    "short_name": "ECIKS",
    "name": "Tuvalu Coastal Adaptation Project",
    "country_id": "TO"
}`
required `x-access-token`
- Find project by name https://opmdata.gem.spc.int/api/project/findById
  ` {
    "short_name":"ECIKS"
}`
- update project by name: https://opmdata.gem.spc.int/api/project/update
  `{
    "short_name": "ECIKS",
    "name": "EWS",
    "country_id": "TO"
}`
required `x-access-token`
- Delete project by name https://opmdata.gem.spc.int/api/project/delete
  `{
    "short_name":"ECIKS"
}`
required `x-access-token`

#### Spatial Projection Model
- List All spatial projection https://opmdata.gem.spc.int/api/spatial_projections
- Add a spatial projection: https://opmdata.gem.spc.int/api/spatial_projection/add
  post: `{
    "name": "EPGS:3939"
}`
required `x-access-token`
- Find spatial projection by id https://opmdata.gem.spc.int/api/spatial_projection/findById
  `{
    "id": "2"
}`
- update spatial projection by id: https://opmdata.gem.spc.int/api/spatial_projection/update
  `{
    "id": "2",
    "name": "EWssssS"
}`
required `x-access-token`
- Delete spatial projection by id https://opmdata.gem.spc.int/api/spatial_projection/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Tag Model
- List All tags https://opmdata.gem.spc.int/api/tags
- Add a tag: https://opmdata.gem.spc.int/api/tag/add
  post: `{
    "name": "dummy"
}`
required `x-access-token`
- Find tagby id https://opmdata.gem.spc.int/api/tag/findById
  `{
    "id": "2"
}`
- update tag by id: https://opmdata.gem.spc.int/api/tag/update
  `{
    "id": "2",
    "name": "xxxxx"
}`
required `x-access-token`
- Delete tag by id https://opmdata.gem.spc.int/api/tag/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Topic Model
- List All topics https://opmdata.gem.spc.int/api/topics
- Add a topic: https://opmdata.gem.spc.int/api/topic/add
  post: `{
    "name": "dummy"
}`
required `x-access-token`
- Find topic by id https://opmdata.gem.spc.int/api/topic/findById
  `{
    "id": "2"
}`
- update topic by id: https://opmdata.gem.spc.int/api/topic/update
  `{
    "id": "2",
    "name": "xxxxx"
}`
required `x-access-token`
- Delete topic by id https://opmdata.gem.spc.int/api/topic/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Metadata Model
- List All metadata https://opmdata.gem.spc.int/api/metadata
- Add metadata: https://opmdata.gem.spc.int/api/metadata/add
  post: `{
    "title":"name of dataset",
    "desciption": "this is the descriptiosssn",
    "temportal_coverage_from":"2016-01-02",
    "temportal_coverage_to": "2016-01-03",
    "rights":"",
    "language":"en",
    "version":"1.0.0",
    "datatypeid":"1",
    "datatype_id":"1",
    "spatial_projection_id":"1",
    "license_id":"1",
    "project_id":"TCAP",
    "publisher_id":"SPC",
    "contact_id":"herved@spc.int",
    "tags":["1"],
    "countries":["TO"],
    "topics":["1"],
    "extents":[{"name":"Minx","value":"179.282882"},{"name":"Miny","value":"-9.282882"}],
    "urls":[{"url":"geoserver-url","path":"179.282882"},{"url":"shared-drive","path":"-9.282882"}]
}` required `x-access-token`
- `title` and `countries` needs to be unique in order to add a metadata successfully.
- Delete metadata by ID: https://opmdata.gem.spc.int/api/metadata/delete
- Find metadata by country https://opmdata.gem.spc.int/api/metadata/findByCountry.
  get `{
    "country":["TO"]
}`
- Find metadata by project https://opmdata.gem.spc.int/api/metadata/findByProject
  get `{
    "project_code":["TCAP"]
}`
- Find metadata by data type https://opmdata.gem.spc.int/api/metadata/findByDataType
  get `{
    "data_type":["Raster"]
}`
- update metadata by id https://opmdata.gem.spc.int/api/metadata/update
  post`{
    "id":"2",
    "title":"name of datswasete",
    "description": "this is the desscriptiosssn",
    "temportal_coverage_from":"2016-01-02",
    "temportal_coverage_to": "2016-01-03",
    "rights":"",
    "language":"en",
    "version":"1.0.0",
    "datatypeid":"1",
    "datatype_id":"1",
    "spatial_projection_id":"1",
    "license_id":"1",
    "project_id":"TCAP",
    "publisher_id":"SPC",
    "contact_id":"divesha@spc.int",
    "tags":["1"],
    "countries":["TO"],
    "topics":["1"],
    "extents":[{"name":"Minx","value":"179.282882"},{"name":"Minz","value":"-9.282882"}],
    "urls":[{"url":"geoserver-url","path":"179.282882"},{"url":"shared-drive","path":"-9.282882"}]
}`
required `x-access-token`
