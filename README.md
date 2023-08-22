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

#### Create Registered Members
To create a user http://localhost:8085/api/auth/signup 
`  {
    "first_name": "divesh",
    "last_name":"anuj",
    "username": "admin",
    "email": "admin@spc.int",
    "password": "admin",
    "roles": ["admineyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9eyJlbWFpbCI6Im"],
    "organization_id":"SPC",
    "country_id":"FJ"
}`

To create a normal user
`
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

To Sign in http://localhost:8085/api/auth/signin post
`{
    "username":"admin",
    "password":"admin"
}`

To refresh the token http://localhost:8085/api/auth/refreshtoken 
`{
    "refreshToken":"2e4a44e0-0f34-4c89-9d41-f9908c9f6f7f"
}`

To access protected pages, pass `x-access-token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6NCwiaWF0IjoxNjkyNjU4NTczLCJleHAiOjE2OTI2NTg2MzN9.9M1sd0PmQKhp4pOlvjF9S9lK-9e2dc91ktQhMiwm4Vo`

To reset password: http://localhost:8085/api/auth/forgotPassword 
`{
    "email":"divesha3@spc.int"
}`

Note: JWT expires in 1 hour and Refresh Token expires in 24 hours. Incase access token has been expired, post refresh token to get a new access token

#### Contact Model
List all contacts: http://localhost:8085/api/contacts

Add contacts: http://localhost:8085/api/contact/add 
post `{
    "first_name":"FJX",
    "last_name":"New",
    "email":"zulfi@spc.int",
    "designation":"hello"
}` required `x-access-token`

Find contact by pk http://localhost:8085/api/contact/findById 
`{
    "email":"divesha@spc.int"
}`

Update a contact by pk http://localhost:8085/api/contact/update 
post body `{
    "email":"divesha@spc.int",
    "first_name":"xxxxx"
}`
required `x-access-token`

Delete contact by email: http://localhost:8085/api/contact/delete 
`{
    "email":"divesha@spc.int"
}`
required `x-access-token`

#### Country Model
- List All countries http://localhost:8085/api/countries
- Add a country: http://localhost:8085/api/country/add
  post: `{
    "short_name":"SM",
    "name":"Solomons"
}`
required `x-access-token`
- Find country by short_name http://localhost:8085/api/country/findById
  ` {
    "short_name":"SM"
}`
- update country by short_name: http://localhost:8085/api/country/update
  `{
    "short_name":"SM",
    "name":"xxxxx"
}`
required `x-access-token`
- Delete country by short_name http://localhost:8085/api/country/delete
  `{
    "short_name":"SM"
}`
required `x-access-token`

#### DataType Model
- List All data types http://localhost:8085/api/datatypes
- Add a datatype: http://localhost:8085/api/datatype/add
  post: `{
    "name":"Point"
}`
required `x-access-token`
- Find country by id http://localhost:8085/api/datatype/findById
  ` {
    "id":"3"
}`
- update country by id: http://localhost:8085/api/datatype/update
  `{
    "id":"3",
    "name":"xxxxx"
}`
required `x-access-token`
- Delete country by short_name http://localhost:8085/api/datatype/delete
  `{
    "id":"3"
}`
required `x-access-token`

#### Extent Model
- List All Extents http://localhost:8085/api/defineextents
- Add a extent: http://localhost:8085/api/defineextent/add
  post: `{
    "name":"dummy"
}`
required `x-access-token`
- Find extent by name http://localhost:8085/api/defineextent/findById
  ` {
    "name":"dummy"
}`
- update extent by name: http://localhost:8085/api/defineextent/update
  `{
    "name_old":"dummy",
    "name_new":"xxxx"
}`
required `x-access-token`
- Delete extent by name http://localhost:8085/api/defineextent/delete
  `{
    "name":"xxxx"
}`
required `x-access-token`

#### URL Model
- List All URLs http://localhost:8085/api/defineurls
- Add a URL: http://localhost:8085/api/defineurl/add
  post: `{
    "name":"dummy"
}`
required `x-access-token`
- Find URL by name http://localhost:8085/api/defineurl/findById
  ` {
    "name":"dummy"
}`
- update URL by name: http://localhost:8085/api/defineurl/update
  `{
    "name_old":"dummy",
    "name_new":"xxxx"
}`
required `x-access-token`
- Delete URL by name http://localhost:8085/api/defineurl/delete
  `{
    "name":"xxxx"
}`
required `x-access-token`

#### License Model
- List All license http://localhost:8085/api/licenses
- Add a license: http://localhost:8085/api/license/add
  post: `{
    "title":"dummy",
    "url":"dummy"
}`
required `x-access-token`
- Find license by id http://localhost:8085/api/license/findById
  ` {
    "id":"2"
}`
- update license by id: http://localhost:8085/api/license/update
  `{
    "id":"2",
    "title":"john",
    "url":"doe"
}`
required `x-access-token`
- Delete license by id http://localhost:8085/api/license/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Organization Model
- List All organizations http://localhost:8085/api/organizations
- Add a organization: http://localhost:8085/api/organization/add
  post: `{
    "short_name":"dummy",
    "name":"dummy"
}`
required `x-access-token`
- Find URL by name http://localhost:8085/api/organization/findById
  ` {
    "short_name":"dummy"
}`
- update URL by name: http://localhost:8085/api/organization/update
  `{
    "name_short_name_old":"dummy",
    "name_short_name_new":"xxxx",
    "name":"hello"
}`
required `x-access-token`
- Delete URL by name http://localhost:8085/api/organization/delete
  `{
    "short_name":"xxxx"
}`
required `x-access-token`

#### Project Model
- List All project http://localhost:8085/api/projects
- Add a project: http://localhost:8085/api/project/add
  post: `{
    "short_name": "ECIKS",
    "name": "Tuvalu Coastal Adaptation Project",
    "country_id": "TO"
}`
required `x-access-token`
- Find project by name http://localhost:8085/api/project/findById
  ` {
    "short_name":"ECIKS"
}`
- update project by name: http://localhost:8085/api/project/update
  `{
    "short_name": "ECIKS",
    "name": "EWS",
    "country_id": "TO"
}`
required `x-access-token`
- Delete project by name http://localhost:8085/api/project/delete
  `{
    "short_name":"ECIKS"
}`
required `x-access-token`

#### Spatial Projection Model
- List All spatial projection http://localhost:8085/api/spatial_projections
- Add a spatial projection: http://localhost:8085/api/spatial_projection/add
  post: `{
    "name": "EPGS:3939"
}`
required `x-access-token`
- Find spatial projection by id http://localhost:8085/api/spatial_projection/findById
  `{
    "id": "2"
}`
- update spatial projection by id: http://localhost:8085/api/spatial_projection/update
  `{
    "id": "2",
    "name": "EWssssS"
}`
required `x-access-token`
- Delete spatial projection by id http://localhost:8085/api/spatial_projection/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Tag Model
- List All spatial projection http://localhost:8085/api/tags
- Add a spatial projection: http://localhost:8085/api/tag/add
  post: `{
    "name": "dummy"
}`
required `x-access-token`
- Find spatial projection by id http://localhost:8085/api/tag/findById
  `{
    "id": "2"
}`
- update spatial projection by id: http://localhost:8085/api/tag/update
  `{
    "id": "2",
    "name": "xxxxx"
}`
required `x-access-token`
- Delete spatial projection by id http://localhost:8085/api/tag/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Topic Model
- List All spatial projection http://localhost:8085/api/topics
- Add a spatial projection: http://localhost:8085/api/topic/add
  post: `{
    "name": "dummy"
}`
required `x-access-token`
- Find spatial projection by id http://localhost:8085/api/topic/findById
  `{
    "id": "2"
}`
- update spatial projection by id: http://localhost:8085/api/topic/update
  `{
    "id": "2",
    "name": "xxxxx"
}`
required `x-access-token`
- Delete spatial projection by id http://localhost:8085/api/topic/delete
  `{
    "id":"2"
}`
required `x-access-token`

#### Metadata Model
- List All metadata http://localhost:8085/api/metadata
- Add metadata: http://localhost:8085/api/metadata/add
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
}`
- title and country needs to be unique in order to add a metadata successfully.
- Delete metadata by ID: http://localhost:8085/api/metadata/delete
- Find metadata by country http://localhost:8085/api/metadata/findByCountry.
  get `{
    "country":["TO"]
}`
- Find metadata by project http://localhost:8085/api/metadata/findByProject
  get `{
    "project_code":["TCAP"]
}`
- Find metadata by data type http://localhost:8085/api/metadata/findByDataType
  get `{
    "data_type":["Raster"]
}`

