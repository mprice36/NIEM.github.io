---
  title: Getting Started with ConTesA
  short: Tutorial
---

{{page.description}}

This introduction to ConTesA will show you how to use ConTesA
to validate a test document for NIEM conformance and how to trace
down common mistakes in developing an NDR conformant document.

## Prerequisites

To complete this tutorial, you'll need internet access and a
[ConTesA account]({{site.data.links.contesa}}/registration).
You'll also need to be familiar with XML and XML Schema.

{:.tip}
> Several parts of this tutorial refer to tools or techniques
> explained in detail under the NIEM IEPD Developer page. We
> recommend you take a look.

<br/>

## Step 1: Create a Data Model

----------------

ConTesA currently uses XML or XML Schema (XSD) as input for
validation against the NIEM Naming and Design Rules (NDR). XSD is
used to prescribe a set of formatting rules for an XML document
(call an XML instance document) and is, itself, specified in XML
format; thus, subject to XSD formatting rules.

In this step, we're going to create a few XML and XSD documents
to input into ConTesA.

### Define Data Requirements

Scenario: One organization would like to represent the relevant
data of traffic accidents, namely crashes, using the NIEM
standard. Let's establish a simple set of data requirements
necessary to represent the relevant information in these "crash"
reports:

* Crash
  * Vehicle
    * Vehicle Identification Number
    * Driver

### Extract NIEM Components

Once we've defined our data requirements we can use the NIEM
Subset Generation Tool (SSGT) to extract the necessary components
to build a NIEM IEPD.

{:.tip}
> SSGT is a great tool for searching the list of prefabricated
NIEM components to prevent extraneous work. Check out the SSGT
tools page if you are not yet familiar with it.

Knowing our requirements and the components of NIEM, our model
might take a form like:

![A simplified graphical model of the Crash data by NIEM
 components](assets/model.png "Crash Data Model by NIEM Components")

{: .note}
> You may [download and save the resulting list of components](assets/wantlist.xml)
> as a NIEM wantlist, which you may [load into the SSGT]({{site.data.links.ssgt}}).

### Construct A Schema

With data requirements, let's construct a test schema. With your
favorite text editor, create a file called
"crash_model_niem_extension.xsd" containing the following text:

<figure>
<figcaption><b>File: <i>crash_model_niem_extension.xsd</i></b></figcaption>
{% highlight xml %}
{% include_relative assets/crash_model_niem_extension.xsd %}
{% endhighlight %}
</figure>

This schema creates founds our model for the Crash data. The
sample IEP from this schema might take the form:

<figure>
<figcaption>
  <b>File: <i>crash_model_niem_extension_instance.xml</i></b>
</figcaption>
{% highlight xml %}
{% include_relative assets/crash_model_niem_extension_instance.xml %}
{% endhighlight %}
</figure>

<br/>

## Step 2: Validating with ConTesA

----------------

Now that we've created the documents to represent our *Crash* data
it's time to validate this model with ConTesA. First, you'll
need to [login]({{site.data.links.contesa}}/login/auth) to your
ConTesA account.

[![Image of ConTesA Login Page](assets/contesa_login.png
   "ConTesA Login Page")]({{site.data.links.contesa}}/login/auth)

Once you've logged into ConTesA, it shows you a dashboard
containing a button to upload a document for validation.

![Image of ConTesA User Home Page](assets/contesa_home.png
  "ConTesA User Home Page")

ConTesA takes two kinds of input documents: an XSD (.xsd) file
or a Zip Archive (.zip) file. Let's upload a Zip Archive of our
Crash example to ConTesA under the file name
"crash_model_niem_extension.zip".

Immediately after you upload the file to ConTesA, it will
automatically run the NIEM NDR set against your documents and
generate a conformance report.

![Image of ConTesA Crash Model validation
  page](assets/contesa_crash_model_extension.png "ConTesA Crash Model Schema Validation Page")

Let's assume we failed rules in developing our schema document
where we did not use the "complexContent" element to specify our
"complexTypes". The bar under the validation for the schema
reflects the level of validation:

{:.tip}
> You can download that misformed schema
> [here](assets/crash_model_niem_extension_bad.xsd).

![Image of ConTesA Validation Summary
  Bar](assets/contesa_validation_summary.png "ConTesA Validation Summary Bar")

<br/>

## Step 3: Understanding the ConTesA Conformance Report

----------------

Let's open the ConTesA conformance report for our
"crash_model_niem_extension.zip":

![Image of ConTesA Crash Model Validation Rules
  Summary](assets/contesa_crash_model_summary.png "ConTesA Crash Model Validation Rules Summary")

In the case where we violated the rules for specifying complex
types, we see a set of rules failed:

![Image of ConTesA Crash Model Validation Rules Bad
  Summary](assets/contesa_crash_model_bad_summary.png "ConTesA Crash Model Validation Rules Bad Summary")

The details of the failed rules follow just below the summary of
the conformance results. This detailed summary gives the status,
line number, rule, and rule text from the NIEM NDR explaining the
validation of the provided document.

![Image of ConTesA Crash Model Rules Bad
](assets/contesa_crash_model_bad_rules.png "ConTesA Crash Model Rules Bad")

Consider rules 9-29 and 9-63 from the NIEM NDR:

{% include ndr-rule.html number="9-29" %}

{% include ndr-rule.html number="9-63" %}

They tell us exactly that lines 42, 48, 78, and 84 in our
misformed XSD are required to be complex content under an
extended type.
