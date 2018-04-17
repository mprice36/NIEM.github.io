---
  title: ConTesA - Conformance Testing Assistant
  short: ConTesA

  contesa_url: "https://tools.niem.gov/contesa"
  tools_catalog_url: "https://www.niem.gov/tools-catalog"
  ndr_url: "https://reference.niem.gov/niem/specification/naming-and-design-rules/4.0/niem-ndr-4.0.html"
  xml_source_url: "https://www.w3.org/XML/"
  json_source_url: "https://www.json.org/"
  rdf_source_url: "https://www.w3.org/RDF/"
---

*[NIEM]: National Information Exchange Model
*[NDR]: Naming and Design Rules
*[IEP]: Information Exchange Package
*[IEPD]: Information Exchange Package Documentation
*[ConTesA]: Conformance Testing Assistant
*[SSGT]: Subset Generation Tool
*[XML]: Extensible Markup Language
*[XSD]: XML Schema Definition
*[JSON]: JavaScript Object Notation
*[RDF]: Resource Description Framework

{{ page.description }}

<div class="introducing-movement">
    <b><i>ConTesA</i> – a web-based NIEM conformance testing tool.</b>
</div>

[![Image of ConTesA Main Page](assets/contesa_main.png
   "ConTesA Main Page")]({{page.contesa_url}})

{% include_relative intro/intro_doc.md %}

# The ConTesA Tool

This introduction to *ConTesA* will show you how to use *ConTesA* to
validate a test document for NIEM conformance and how to trace down
common mistakes in developing a NIEM conformance document.

## Prerequisites

To complete this tutorial, you'll need internet access and a
[ConTesA account]({{page.contesa_url}}/registration). You'll also need
to be familiar with at least one of the supported NIEM data formats
(i.e. [XML]({{page.xml_source_url}}), [JSON]({{page.json_source_url}}),
or [RDF]({{page.rdf_source_url}})) and your favorite text editor.

{:.tip}
> Several parts of this tutorial refer to tools or techniques explained
> in detail under the [NIEM IEPD Developer](../../../iepd-developer)
> training page. We recommend you take a look.

{:.note}
> We use XML as the data format for in this tutorial.

## Step 1: Create a Data Model

----------------

*ConTesA* currently uses XML or XML Schema (XSD) as input for validation
against the [NIEM Naming and Design Rules (NDR)]({{page.ndr_url}}). XSD
is used to prescribe a set of formatting rules for an XML document (call
an XML instance document) and is, itself, specified in XML format; thus,
subject to XSD formatting rules.

In this step, we're going to create a few XML and XSD documents to input
into *ConTesA*.

### Define Data Requirements

Scenario: One organization would like to represent the relevant data of
traffic accidents, namely crashes, using the NIEM standard. Let's 
establish a simple set of data requirements necessary to represent the
relevant information in these "crash" reports:

* Crash Driver Information
  * Person
    * Date of Birth
    * Name
  * Crash
    * Incident Location
    * Vehicle
      * Driver
        * Role
        * License
      * Vehicle Identification Number

### Extract NIEM Components

Once we've defined our data requirements we can use the NIEM
Subset Generation Tool (SSGT) to extract the necessary components
to build a NIEM IEPD.

{:.tip}
> SSGT is a great tool for searching the list of prefabricated
NIEM components to prevent extraneous work. Check out the [SSGT
tools page](../ssgt) if you are not yet familiar with it.

Knowing our requirements and the components of NIEM, our model
might take a form like:

![A simplified graphical model of the Crash data by NIEM
 components](assets/model.png "Crash Data Model by NIEM Components")

{: .note}
> You may [download and save the resulting list of components](assets/wantlist.xml)
> as a NIEM wantlist, which you may
> [load into the SSGT](https://tools.niem.gov/niemtools/ssgt/SSGT-Options.iepd).

### Construct A Schema

With data requirements, let's construct a test schema. With your
favorite text editor, create a file called "crash_model_niem_extension.xsd"
containing the following text:

<figure>
<figcaption><b>File: <i>crash_model_niem_extension.xsd</i></b></figcaption>
{% highlight xml %}
{% include_relative assets/crash_model_niem_extension.xsd %}
{% endhighlight %}
</figure>

This schema creates founds our model for the Crash data. The sample IEP
from this schema might take the form:

<figure>
<figcaption><b>File: <i>crash_model_niem_extension_instance.xml</i></b></figcaption>
{% highlight xml %}
{% include_relative assets/crash_model_niem_extension_instance.xml %}
{% endhighlight %}
</figure>

## Step 2: Validating with ConTesA

----------------

Now that we've created the documents to represent our *Crash* data
it's time to validate this model with *ConTesA*. First, you'll need
to [login]({{page.contesa_url}}/login/auth) to your *ConTesA* account.

[![Image of ConTesA Login Page](assets/contesa_login.png
   "ConTesA Login Page")]({{page.contesa_url}}/login/auth)

Once you've logged into *ConTesA*, it shows you a dashboard containing
a button to upload a document for validation.

![Image of ConTesA User Home Page](assets/contesa_home.png
  "ConTesA User Home Page")

*ConTesA* takes two kinds of input documents: an XSD (.xsd) file or a
Zip Archive (.zip) file.

![Image of ConTesA Crash Model's schema validation
  page](assets/contesa_crash_model_schema.png "ConTesA Crash Model Schema
  Validation Page")

![Image of ConTesA Validation Summary
  Bar](assets/contesa_validation_summary.png "ConTesA Validation Summary Bar")
