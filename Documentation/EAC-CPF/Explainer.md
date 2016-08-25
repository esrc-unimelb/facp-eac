***Find & Connect Data Explainer***

**Find & Connect’s data is available as XML outputs using the EAC-CPF schema, however it does not use all the Elements in a standard way. **

**This explainer will highlight some of the key information that will help you use and understand the Find & Connect data.**

***Types of entities***

Valid types of entity for the dataset are: Organisation, Legislation, Event, Archival Series, Archival Collection, Archival Item, Concept, Contact Details, Glossary Term, and Place.

NOTE: “Home” is not a valid type of entity for the dataset.

NOTE: The schema element &lt;entityType&gt; does not hold relevant information for this dataset.

Instead:

&nbsp;&nbsp;&nbsp;&nbsp;&lt;control&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;localControl localType="**typeOfEntity**"&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;term&gt;**TypeOfEntity**&lt;/term&gt;

***Functions - Homes***

Function attributes describe the different functions of an entity. An entity may have multiple functions.

“Home” is a key function for this dataset and indicates an organisation that provided residential care.

NOTE: Every Home has the localType=”typeOfEntity” Organisation, BUT not every Organisation has the function of Home.

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;description&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;functions&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;function&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;term&gt;**FunctionName**&lt;/term&gt;

***Names of entities ***

Name attributes indicate the name(s) by which an entity is known.

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;identity&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;nameEntry&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;part&gt;**Name**&lt;/part&gt;

An entity may have additional name attributes to indicate any alternate names it is known by.

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;identity&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;nameEntry localType=""&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;part&gt;**ALTERNATE NAME**&lt;/part&gt;

***Date range of entities ***

This field will not always be completed, but provides the data range for relevant entity types, including Organisations (and therefore Homes).

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;description&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;existDates&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;dateRange&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;fromDate standardDate="**yyyy-mm-dd**"&gt;**yyyy**&lt;/fromDate&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;toDate standardDate="**yyyy-mm-dd**"&gt;**yyyy**&lt;/toDate&gt;

***Record ID vs Entity ID***

Record ID is the database unique ID for the entity. The Find and Connect dataset is drawn from nine jurisdictional databases, with each database using a different prefix for Record ID. The Record ID can be used to determine which database an entity is stored in and provides a means of applying state-based filters. The start of the ID reflects the jurisdiction.

| **Record ID** | **Jurisdiction** |
|---------------|------------------|
| FE\#\#\#\#\#  | Australia (federal)        |
| AE\#\#\#\#\#  | ACT              |
| NE\#\#\#\#\#  | NSW              |
| YE\#\#\#\#\#  | NT               |
| QE\#\#\#\#\#  | QLD              |
| SE\#\#\#\#\#  | SA               |
| TE\#\#\#\#\#  | TAS              |
| E\#\#\#\#\#\# | VIC              |
| WE\#\#\#\#\#  | WA               |

&nbsp;&nbsp;&nbsp;&nbsp;&lt;control&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;recordId&gt;**XXXXXXX**&lt;/recordId&gt;

Entity ID is the URL of the entity’s page on [www.findandconnect.gov.au](http://www.findandconnect.gov.au). The ID is expressed as http://www.findandconnect.gov.au/ref/ **JURISDICTION**/biogs/**recordID**b.htm

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;identity&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;entityId&gt;http://www.findandconnect.gov.au/ref/**XXX**/biogs/**recordID**b.htm&lt;/entityId&gt;

***How do I find the location of a Home?***

Descriptive and location data about Homes are in &lt;biogHist&gt;. The &lt;chronItem&gt; will include the name of city or suburb, e.g. Ballarat or Carlton, the start date and end date of the entity being located at that place and the street address, prefixed by text.

NOTE: The &lt;event&gt; string will only contain an address if the first word in the string is “Address” or “Location”.

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;description&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;biogHist&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;chronList&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;chronItem&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;dateRange&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;fromDate standardDate="**yyyy-mm-dd**"&gt;**yyyy**&lt;/fromDate&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;toDate standardDate="**yyyy-mm-dd**"&gt;**yyyy**&lt;/toDate&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;placeEntry&gt;**PlaceName**&lt;/placeEntry&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;event&gt;**Address/Location** - **Entity** was located **at Street Address, Suburb**&lt;/event&gt;

***Where is the description of a Home?***

A brief description of a Home is available in the &lt;abstract&gt;. If more detail is available it is found in the subsequent &lt;p&gt; tags. There is no limit on how many paragraphs may follow the abstract.

&nbsp;&nbsp;&nbsp;&nbsp;&lt;cpfDescription&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;biogHist&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;abstract&gt;**Brief Description**&lt;/abstract&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p&gt;**additional paragraph 1**&lt;/p&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p&gt;**additional paragraph 2**&lt;/p&gt;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **…**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p&gt;**additional paragraph 8**&lt;/p&gt;
