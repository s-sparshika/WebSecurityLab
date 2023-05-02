# XML
 XML stands for Extensible Markup Language. It is a markup language that is used to store and transport data. XML uses tags to define elements, attributes, and values, which are used to structure and describe the data. 
 XML is a flexible and standardized format that can be used for a wide variety of applications, such as data exchange between different software systems, web services, and configuration files. 
 XML is often used as a data interchange format because it is both human-readable and machine-readable. 

## XML Document Example

    <?xml version="1.0" encoding="UTF-8"?>
    <!-- This XML document describes a DVD library -->
    <library>
      <dvd id="1">
        <title>Gone with the Wind</title>
        <format>Movie</format>
        <genre>Classic</ genre >
      </dvd>
      <dvd id="2">
        <title>Star Trek</title>
        <format>TV Series</format>
        <genre>Science fiction</genre>
      </dvd>
    </library>
    
# DTD (Document Type Definition)
DTD stands for Document Type Definition. It is a set of rules that defines the structure and elements of an XML document. 
A DTD is used to validate the content of an XML document and ensure that it conforms to a specific format or schema.
A DTD is essentially a blueprint or template for an XML document. It defines the elements that can be used in the document, their order, and the attributes that they can have. 
It also specifies any constraints on the content, such as whether an element is required or optional, whether it can occur multiple times, and what types of data are allowed for its attributes.

### DTD example

    <?xml version="1.0" encoding="UTF-8"?>
    <!ELEMENT library (dvd+)>
    <!ELEMENT dvd (title, format, type)>
    <!ELEMENT title (#PCDATA)>
    <!ELEMENT format (#PCDATA)>
    <!ELEMENT genre (#PCDATA)>
    <!ATTLIST dvd id CDATA #REQUIRED>

### Declaring Elements

    <!ELEMENT elementName (elementContent)>
    
### Elements with data

    <!ELEMENT elementName (#CDATA)>
    <!ELEMENT elementName (#PCDATA)>
    <!ELEMENT elementName (ANY)>
    
`#CDATA` - The element contains character data that is not supposed to be parsed by a parser for nested elements.

`#PCDATA` - The element contains data that is going to be parsed by a parser for nested elements.

`ANY` - Declares an element with any content as its value.

# Associating DTD Declarations to XML Documents
- To specify that an XML document is an instance of an XML dialect specified by a set of DTD declarations, it can be done in two ways:
## Method 1: DTD declarations are to be included in your XML document
`<!DOCTYPE rootElementTag [DTD-Declarations]>`
![image](https://user-images.githubusercontent.com/68326118/235574846-67f0e854-fe6a-4669-b849-fdea781ef456.png)
## Validation
![image](https://user-images.githubusercontent.com/68326118/235597742-db121fd3-2a2d-49c8-b3f8-1103d572acee.png)

## Method 2: To link a DTD declaration file to an XML document
`<!DOCTYPE rootElementTag SYSTEM DTD-URL>`
![image](https://user-images.githubusercontent.com/68326118/235575194-c6112e46-3ee6-4cac-97d2-cfaa449f39c2.png)
## Validation
![image](https://user-images.githubusercontent.com/68326118/235597878-06922746-ce67-45c6-8d89-77e723edb3bb.png)

# XML Schema
While Document Type Definition (DTD) is a part of the XML specification and is supported by all XML processors, it has limitations in defining complex data structures. XML Schema is an industry standard alternative to DTD for defining XML dialects. XML Schema is itself an XML dialect, so it can benefit from many existing XML techniques and processors. It provides a more comprehensive way to define the data structure and its constraints, 
allowing for the reuse of common declarations in multiple element or attribute declarations.

![image](https://user-images.githubusercontent.com/68326118/235575414-e1a2f82e-5c6a-47c9-a989-305e9c8b8db6.png)

## Validation
![image](https://user-images.githubusercontent.com/68326118/235598048-cf362aad-7321-4669-b2b5-adaeb520c3b5.png)

In the above example "xs" - XML prefix representing namesapce;
`http://www.w3.org/2001/XMLSchema`- Here if the element is  qualified by its namespace prefix, as “xs:element” for element element declared in namespace `“http://www.w3.org/2001/XMLSchema”`, 
its attributes and nested elements by default belong to the same namespace.

# Referencing XML Schema Specification in an XML Document
## With Namespace
Attribute - `schemaLocation`

    <rootTag
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="namaspaceString schemaFileURL"
    >

## Without Target Namespace
    <rootTag
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-
    instance"
    xsi:schemaLocation=
    "namaspaceString schemaFileURL"
    >

# XML Parsing and Validation with SAX and DOM
Most XML applications require parsing and processing of XML documents. SAX and DOM are two popular parsers used for this purpose. SAX reads the XML document sequentially and triggers events when it detects language features like elements and attributes. It is efficient for applications that do not need to search information backwards in an XML document. On the other hand, DOM builds a complete tree data structure in computer memory, making it more convenient for detailed document analysis and language transformation. Both parsers can work in validation mode to check if the input XML document is well-formed and if it is an instance of the XML dialect when provided with the XML dialect specification in DTD or XML Schema.
