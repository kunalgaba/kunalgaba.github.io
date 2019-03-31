---
layout: post
title:  "AEM XML Addon - Manage DITA content in AEM"
date:   2019-03-29 16:02:15
categories: AEM
---
# AEM XML Addon

A new feature in AEM which allows you to manage new type of content. Yes if you manage technical documentation or content in [DITA](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=dita) file format then
you should consider using Adobe AEM XML Addon solution. This solution requires buying a separate license just like AEM Assets and Forms and does not come with standard AEM license.


# DITA Standard

The Darwin Information Typing Architecture or Document Information Typing Architecture (DITA) is an XML data model for authoring and publishing. It is an open standard that is defined and maintained by the OASIS DITA Technical Committee.
All technical documentation which is structured content and organized in the form of toics and maps(table of contents) can be maintained in DITA formats. There are many Desktop based editors like Oxygen XML Editor are available for authoring
DITA content.

# XML Addon features and capabilities
XML Addon provides you the capability to author DITA content using powerful in built web editor and it also allows you to publish the content in the form of AEM site pages. There are other output formats but in many projects customers will be
asking for building consumption pages where the technical documentation is available and searchable in a website.
You can read more about key XML Addon capabilities and feature here - https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html

# Key design and architecture considerations for any XML Addon implementation

## Migration of content
* If you are migrating content from external application to AEM then you will have to write a script to convert the content first to valid DITA format. XML Addon provides some plugins for converting the Word, PDF or XHTML documents to DITA.
  You should consider those plugins for conversion rather than writing custom code for the conversion.
* Even if the source content is in DITA format even then you will have to write a custom migration script because DITA content in AEM once migrated should be compatible with AEM web editor.
    * * For example - All links to assets and topics in AEM DITA files are maintained as relative paths whereas in the source files they may be absolute.
* All links to assets should be resolved properly in AEM. This means the Assets (Document and Images) will have to be imported in AEM as well.
* You should import the Assets files first and then import the DITA files.



