---
  title: ConTesA - Conformance Testing Assistant
  short: ConTesA
---

{% assign contesa_url = "https://tools.niem.gov/contesa" %}
{% assign tools_catalog_url = "https://www.niem.gov/tools-catalog" %}
{% assign ndr_url = "https://reference.niem.gov/niem/specification/naming-and-design-rules/4.0/niem-ndr-4.0.html" %}
{% assign xml_source_url = "https://www.w3.org/XML/" %}
{% assign json_source_url = "https://www.json.org/" %}
{% assign rdf_source_url = "https://www.w3.org/RDF/" %}

{{ page.description }}

<div class="introducing-movement">
	<b><i>ConTesA</i> – a web-based NIEM conformance testing tool.</b>
</div>
<div class="access-tool-here">
	<a class="btn btn-primary btn" href="{{contesa_url}}" target="_blank">
	  <span class="content">Visit ConTesA</span>
	</a>
</div>

{% include_relative intro/index.md %}


## The ConTesA Tool
-------------------
This introduction to *ConTesA* will show you how to use *ConTesA* to
validate a test document for NIEM conformance and how to trace down
common mistakes in developing a NIEM conformant document.

### Prerequisites

To complete this tutorial, you'll need internet access and a
[ConTesA account]({{contesa_url}}/registration). You'll also need to be
familiar with at least one of the supported NIEM data formats (i.e.
[XML]({{xml_source_url}}), [JSON]({{json_source_url}}), or
[RDF]({{rdf_source_url}})) and your favorite text editor.

{:.note}
> We use XML as the data format for in this tutorial.


## Step 1: Create a Document
----------------------------
*ConTesA* currently uses XML or XML Schema (XSD) as input for validation
against the NIEM NDR. XSD is used to prescribe a set of formatting rules
for an XML document (call an XML instance document) and is, itself,
specified in XML format; thus, subject to XSD formatting rules.

In this step, we're going to create a few XML and XSD documents to input
into *ConTesA*.

### A Naive XML Document

Let's create a simple XML document with no prior knowledge of the NIEM
NDR. In your favorite text editor, create the following document and
name it "naive.xml":

<figure>
<figcaption><b>File: <i>naive.xml</i></b></figcaption>
{% highlight xml %}
<?xml version="1.0"?>
<Start>
  <Text1 attri="Some Attribute">This is the first text.</Text1>
  <Text2>This is more text.</Text2>
</Start>
{% endhighlight %}
</figure>

This document is valid XML; it follows all of the standard XML 1.0 rules
and is straightforward to parse with any well-founded XML parser. However,
this document is not NIEM compliant. In [Step 3](#step-3-review-the-conformance-report)
we'll see how *ConTesA* evaluates this document against the NIEM NDR.

### Moving Towards NIEM

In this second document, let's try to be a bit more NIEM aware. Rule 12-1
of the NIEM NDR requires, in so many words, that an XML instance document
must reference a valid set of NIEM compliant schemas:

{% include ndr-rule.html number="12-1" %}

To that end, let's first create a NIEM compliant XSD document and then
use that document to generate a conformant XML instance document.


## Step 2: Upload to ConTesA
----------------------------
We are borg.


## Step 3: Review the Conformance Report
----------------------------------------
I broke the rules...


## Next Steps...
----------------
Get a job...
