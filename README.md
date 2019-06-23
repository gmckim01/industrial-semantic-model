# industrial-semantic-model
A semantic modeling technique for the organization of data for heavy asset industries (power generation, chemicals and petroleum, and other process industries).

According to Technopedia, a Semantic Model is defined as "...[a] data model is a method of structuring data in order to represent it in a specific logical way. It is a conceptual data model that includes semantic information that adds a basic meaning to the data and the relationships that lie between them. This approach to data modeling and data organization allows for the easy development of application programs and also for the easy maintenance of data consistency when data is updated." (https://www.techopedia.com/definition/30489/semantic-data-model).  A Semantic Model for heavy industries is intended to address several information management challenges associated with modeling the huge amount of static data (drawings, specifications, vendor data sheets, schematics, bill-of-materials, shop drawings, etc.) and dynamic data (time series historian data, asset management logs, etc.).

The semantic modeling technique applied here uses the Neo4j graph database.  Graph databases are an excellent means of managing and querying data that has a lot of "many-to-many" relationships.  For data in and about heavy industries, these relationships take several forms:

a) equipment/component/system taxonomic hierarchies
b) asset class definitions, composability, and inheritence of attributes and behaviors
c) topological relationships: connectivity of assets
d) normalization of "namespaces," across different systems-of-record

The technique shared herein uses a set of script files, containing Neo4j Cypher queries, and an Excel file, with multiple tabs of tables in .csv format.  The user updates the Excel spreadsheet to reflect what the plant/network/system/assets they are modeling, exports the file in .csv format, copies the Cypher script file, and then pastes it as a query in Neo4j.  The script parses the .csv file, creating an asset class schema, and then creating instances of assets, connections, instruments, problem codes, etc.
