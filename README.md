Peace Corps Countries & Regions REST API
==========================
<i><h3>Version 1.0</h3></i>

<h4>Peace Corps Countries & Regions Dataset</h4>
<p>The Peace Corps Countries dataset includes all countries Peace Corps Volunteers have served in and are currently serving in. The Peace Corps Regions dataset includes all the Peace Corps regions.</p>

<h4>Countries and Regions API</h4>
<p>The Peace Corps Countries & Regions REST API provides read-only access and currently supports JSON data format. Individual users (per IP) are limited to 15 requests per second. Developers, designers, engineers, and partners are all encouraged to leverage the Peace Corps Countries & Regions API to build innovative tools and/or creatively share data.</p>

<p>Alternatively, for a static XML list of current Peace Corps Countries & Regions, <a href="http://www.peacecorps.gov/volunteer/learn/wherepc/regions_countries.xml" target="_blank">click here</a>. <i>Note: This is a static dataset that does not support any filtering arguments,
and may not include all the country and region elements/fields that are included in the API.</i></p>
____

<h4>Country API Elements</h4>

| Name          | Type           | Description                       |
| ------------- |:--------------:| :---------------------------------|
| id            | Number         | Unique country identifier. |
| name          | String         | Country name.              |
| slug          | String         | Country slug.              |
| region        | String         | Region slug.               |
| description   | Text           | Country description.       |
| current       | Boolean        | Used to mark a Peace Corps country as presently active (true). |
| is_suspended  | Boolean        | Used to mark a Peace Corps country as presently suspended (true). |
| program_dates | String         | Country Peace Corps program dates. |
| volunteers    | Number         | Number of active volunteers. |
| cumulative    | Number         | Number of cumulative volunteers. |
| popuplation   | String         | Population average.        |
| sectors       | Text           | Peace Corps program sectors. |
| languages     | String         | Languages spoken.          |
| pcr           | Boolean        | Peace Corps Response       |
| projects_list | Text           | Volunteer projects list.   |
| flickr_id     | String         | Flickr set ID.             |
| flag_image    | String         | Flag image URL. (300px width) |
| banner_image  | String         | Banner image URL. (800px x 214px) |
| videos - title| String         | Video title.               |
| videos - youtube_id | String   | Video YouTube ID.               |
| medical_considerations | Text  | Country medical considerations. |
| country_page_url | String      | Country page URL           |
| mobile_country_page_url | String | Mobile country page URL. |
| country_site_url | Text        | Country site URL.          |

<h4>Region API Elements</h4>

| Name          | Type           | Description                       |
| ------------- |:--------------:| :---------------------------------|
| id            | Number         | Unique region identifier.  |
| name          | String         | Region name.               |
| slug          | String         | Region slug.               |
| description   | Text           | Region description.        |
| region_page_url | String       | Region page URL.           |

____

<h4>Resources</h4>
<b>GET </b>`/api/v1/geography/countries/`<br/>
<b>GET </b>`/api/v1/geography/countries/{country-slug}`<br/>
<b>GET </b>`/api/v1/geography/regions/`<br/>
<b>GET </b>`/api/v1/geography/regions/{region-slug}`<br/>

____

<h4>GET <i>/api/v1/geography/countries/</i></h4>
<p>Returns a list of all Peace Corps countries. You can filter the results by using the following query parameters/arguments in the URL:</p>

<h5>Arguments</h5>
| Argument      | Description    | Keyword                    |
| ------------- |:--------------| :---------------------------------|
| country       | Filter by country/countries. <br/> `(e.g. ?country=benin)` <br/> <i>Note: You may filter by multiple countries. The following arguments in the URL will return both Benin and Albania.</i> <br/> `?country=benin&country=albania`        | Use country slug.  |
| region        | Filter by region/s. <br/> `(e.g. ?region=africa)` <br/> <i>Note: You may filter by multiple regions. The following arguments in the URL will return all countries within Eastern Europe and Africa.</i> <br/> `?region=easteurope&region=africa`        | Use region slug.               |
| sector          | Filter by sector/s. <br/> `(e.g. ?sector=health)` <br/> <i>Note: Filtering by multiple sectors is <b>NOT</b> supported.</i>         | Use a keyword from the six Peace Corps sectors: <br/> <ul><li>agriculture</li><li>community</li><li>education</li><li>environment</li><li>health</li><li>youth</li><ul>           |
| current   | Filter by active or inactive countries. True being active countries and false being inactive countries. <br/> `(e.g. ?current=true)`           | Use ‘true’ or ‘false’.        |
| suspended | Filter by suspended or non-suspended countries. True being suspended and false being not suspended. <br/> `(e.g. ?suspended=true)`       | Use ‘true’ or ‘false’           |

<h5>Request Example</h5>
`http://www.peacecorps.gov/api/v1/geography/countries/?region=caribbean&current=true`
<h5>Response Example</h5>
```json
[
{
id: 68,
name: "Dominican Republic",
slug: "dominicanrepublic",
region: "caribbean",
description: "<p> More than 4,220 Peace Corps Volunteers have served in Dominican Republic since the program was established in 1962. Currently, 220 Volunteers serve in Dominican Republic. Volunteers work in the areas of community development, health, education, environment and business. Volunteers are trained and work in Spanish and basic Haitian Kreyol.</p> ",
current: true,
is_suspended: false,
program_dates: "1962 - present",
volunteers: 220,
cumulative: 4224,
population: "9 million",
sectors: "<p> Business Development, Community Development, Education, Environment, Health</p> ",
languages: "Spanish and basic Haitian Kreyol",
pcr: false,
projects_list: "<h2> Make a Contribution</h2> <p> Learn more about Volunteer projects and how your contribution helps.</p> <p> <a href=" ">Volunteer Projects in Dominican Republic</a></p> ",
flickr_id: "72157626217383233",
flag_image: "http://files.peacecorps.gov/uploads/countries/flags/Dominican_Republic.gif",
banner_image: "http://files.peacecorps.gov/uploads/countries/banners/dominicanrepublic.jpg",
videos: [ ],
medical_considerations: "",
country_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/caribbean/dominicanrepublic/",
mobile_country_page_url: "http://www.peacecorps.gov/mobile/where-volunteers-serve/dominicanrepublic/",
country_site_url: "http://dominican.peacecorps.gov/"
},
{
id: 69,
name: "Eastern Caribbean",
slug: "easterncaribbean",
region: "caribbean",
description: "<p> More than 3,770 Peace Corps Volunteers have served in Eastern Caribbean since the program was established in 1961. Currently, 115 Volunteers serve in Eastern Caribbean. Volunteers work in the areas of community development, business and education. Volunteers are trained and work in English and French Creole (Kweyol).</p> ",
current: true,
is_suspended: false,
program_dates: "1961 - present",
volunteers: 115,
cumulative: 3771,
population: "93,000",
sectors: "<p> Business Development, Community Development, Education</p> ",
languages: "English and French Creole (Kweyol)",
pcr: false,
projects_list: "<h2> Make a Contribution</h2> <p> Learn more about Volunteer projects and how your contribution helps.</p> <p> <a href=" ">Donate to Volunteer Projects in Eastern Caribbean</a></p> ",
flickr_id: "72157626217574219",
flag_image: "http://files.peacecorps.gov/uploads/countries/flags/Eastern_Caribbean_1.jpg",
banner_image: "http://files.peacecorps.gov/uploads/countries/banners/easterncaribbean.jpg",
videos: [ ],
medical_considerations: "",
country_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/caribbean/easterncaribbean/",
mobile_country_page_url: "http://www.peacecorps.gov/mobile/where-volunteers-serve/easterncaribbean/",
country_site_url: " http://easterncaribbean.peacecorps.gov "
},
{
id: 70,
name: "Jamaica",
slug: "jamaica",
region: "caribbean",
description: "<p> More than 3,720 Peace Corps Volunteers have served in Jamaica since the program was established in 1962. Currently, 58 Volunteers serve in Jamaica. Volunteers work in the areas of education, community and youth development, environment and agriculture. Volunteers are trained and work in Jamaican Patois.</p> ",
current: true,
is_suspended: false,
program_dates: "1962 - present",
volunteers: 58,
cumulative: 3724,
population: "3 million",
sectors: "<p> Agriculture, Community Development, Education, Environment, Youth Development</p> ",
languages: "Jamaican Patois",
pcr: false,
projects_list: "<h2> Make a Contribution</h2> <p> Learn more about Volunteer projects and how your contribution helps.</p> <p> <a href=" ">Donate to Volunteer Projects in Jamaica</a></p> ",
flickr_id: "72157626226192659",
flag_image: "http://files.peacecorps.gov/uploads/countries/flags/Jamaica.gif",
banner_image: "http://files.peacecorps.gov/uploads/countries/banners/jamaica.jpg",
videos: [ ],
medical_considerations: "",
country_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/caribbean/jamaica/",
mobile_country_page_url: "http://www.peacecorps.gov/mobile/where-volunteers-serve/jamaica/",
country_site_url: " http://jamaica.peacecorps.gov"
}
]

```
____

<h4>GET <i>/api/v1/geography/countries/{country-slug}</i></h4>
<p>Returns a single country according to what country slug is added to the URL.</p>

<h5>Request Example</h5>
`http://www.peacecorps.gov/api/v1/geography/countries/belize`
<h5>Response Example</h5>
```json

{
id: 72,
name: "Belize",
slug: "belize",
region: "centralamerica",
description: "<p> More than 1,910 Peace Corps Volunteers have served in Belize since the program was established in 1962. Currently, 82 Volunteers serve in Belize. Volunteers work in the areas of education, business and organizational development, and health. Volunteers are trained and work in Garifuna, Q&#39;eqchi, Kriol, Mopan, and Spanish.</p> ",
current: true,
is_suspended: false,
program_dates: "1962-present",
volunteers: 82,
cumulative: 1917,
population: "250,000",
sectors: "<p> Business and Organizational Development, Education, Health</p> ",
languages: "Garifuna, Q'eqchi, Kriol, Mopan, and Spanish",
pcr: false,
projects_list: "<h2> Make a Contribution</h2> <p> Learn more about Volunteer projects and how your contribution helps.</p> <p> <a href=" ">Donate to Volunteer Projects in Belize</a></p> ",
flickr_id: "72157625949111704",
flag_image: "http://files.peacecorps.gov/uploads/countries/flags/Belize.gif",
banner_image: "http://files.peacecorps.gov/uploads/countries/banners/belize.jpg",
videos: [ ],
medical_considerations: "",
country_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/centralamerica/belize/",
mobile_country_page_url: "http://www.peacecorps.gov/mobile/where-volunteers-serve/belize/",
country_site_url: "http://belize.peacecorps.gov "
}


```
____

<h4>GET <i>/api/v1/geography/regions/</i></h4>
<p>Returns a list of all Peace Corps regions. You can filter the results by using the following query parameter/argument in the URL:</p>

<h5>Arguments</h5>
| Argument      | Description   | Keyword                       |
| ------------- |:--------------| :---------------------------------|
| region        | Filter by region/s. <br/> `(e.g. ?region=africa)` <br/> <i>Note: You may filter by multiple regions. The following arguments in the URL will return both the Africa and Asia region.</i> <br/> `?region=africa&region=asia`        | Use region slug.  |

<h5>Request Example</h5>
`http://www.peacecorps.gov /api/v1/geography/regions/?region=africa&region=asia`
<h5>Response Example</h5>
```json

[
{
id: 16,
name: "Africa",
slug: "africa",
description: "<p> Peace Corps Volunteers respond to various needs that impact Africa&#39;s development. These include the importance of HIV/AIDS prevention and education, girls&#39; education, the increasing pressures of environmental degradation, advances in information technology, and the democratization process that some countries are committed to supporting.</p> <p> Peace Corps has continued to develop a strong partnership with the people of Africa. Volunteers currently work in the areas of education, health and HIV/AIDS, business development, agriculture, and the environment.</p> ",
region_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/africa/"
},
{
id: 13,
name: "Asia",
slug: "asia",
description: "<p> Volunteers in Asia play important roles in helping people address changing and complex needs in the areas of education, business, the environment, and health.</p> ",
region_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/asia/"
}
]


```
____

<h4>GET <i>/api/v1/geography/regions/{region-slug}</i></h4>
<p>Returns a single region according to what region slug is added to the URL.</p>

<h5>Request Example</h5>
`http://www.peacecorps.gov/api/v1/geography/regions/centralamerica/`
<h5>Response Example</h5>
```json

{
id: 10,
name: "Central America and Mexico",
slug: "centralamerica",
description: "<p> Volunteers have the opportunity to experience the rich cultural heritage and geographic diversity that make any one of these Central American nations a challenging and rewarding country of service.</p> ",
region_page_url: "http://www.peacecorps.gov/volunteer/learn/wherepc/centralamerica/"
}


```
<br/>
<br/>
<b>Note:</b> A PDF file of the documentation for this API can be found in the 'API Documentation' folder within this repo.
