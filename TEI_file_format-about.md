# About TEI Files

TEI and XML have a lot in common. If you are new to both, and if HTML is still a strange thing to you, then there's a lot more you are probably going to want to know than I can explain here. 

Perhaps it would help to note that all of them -- TEI, XML, HTML -- are markup languages and as such are basically designed to wrap tags around the kind of content you are used to thinking about. In fact, one way to understand them is that they allow you to place your thinking about a text in the text itself. 

It would also probably help to know that of the three, TEI is the most forgiving and also the most flexible. There are a few rules you need to follow, but those rules are really about making sure that information is easily found either by human readers or by machines being directed by humans. E.g., no human wants to have to go hunting for a publication date, and no human wants to have to describe to a machine how to go hunting for a publication date. 

That noted, a brief refresher of basic parts and pieces in a TEI document can't hurt. TEI documents, like XML and HTML documents, are written, for the most part, by enclosing information within tags to make an element:

    <title>The Amazing Crawfish Boat</title>

Also like XML and HTML, elements can be qualified by adding attributes inside the start tag:

    <date when="2015"/>

The element above is also an example of a self-contained, or self-closing element. These occur in TEI and not in XML, because TEI is designed to deal with the messiness of human texts in a very forgiving fashion, and sometimes that means using an oddity like a self-enclosed tag.

## Basic File Structure

The best way to learn the basic structure of a TEI file is to look at one. There are several included in this repository. If nothing else, if you look at one, you will note that it looks a lot like an HTML file:

* There is a document type declaration at the top that announces that it's a TEI file.
* There is a header.
* There is a body.
* And then there is a tag that closes up the TEI file. (Because, you know, computers.)

The fundamental structure of a TEI document is:

	<TEI>
	
	<teiHeader>
		</teiHeader>
	
	<text>
		</text>
	
	</TEI>
	

It couldn't be any simpler. So, let's take a look at the two parts of the document which will preoccupy us most of the time, the header and the body.


## The Header

The `teiHeader` has four major parts:

`<fileDesc>`: the *file description* contains a full bibliographic description of an electronic file.

`<encodingDesc>`: the *encoding description* documents the relationship between an electronic text and it source or sources.

`<profileDesc>`: the *text-profile description* provides a detailed description of non-bibliographic aspects of a text, specifically the languages and sublanguages used, the situation in which it was produced, the participants and their setting.

`<revisionDesc>`: *revision description* summarizes the revision history for a file.


## The Body

Literary and historical documents often have come in clearly divided parts, with `front` and `back` elements in addition to the `body` element. Folklore and oral history records will tend only to have a body or, more simply, a `text`. Multiple texts are possible within a TEI document, though they are sometimes referred to as a `corpus`. Corpora can be in a single document, or they can be in multiple documents but indexed by a single document. You can regard this as confusing or as flexible.

Many of the elements that you might be used to from HTML are present in TEI, especially if you are familiar with more recent versions of HTML, which has developed tag frameworks for things like `article`:

- `<q>` is used for quotations. 
- `<emph>` marks words or phrases which are stressed or emphasized for linguistic or rhetorical effect.
- `<term>` contains a single-word, multi-word, or symbolic designation which is regarded as a technical term.
- `<mentioned>` marks words or phrases mentioned, not used.

Folklorists and oral historians should know that they have two options when it comes to marking up texts: segmenting oral discourse either into sentences or into lines, depending upon their orientation:

`<l>` indicates a line.
`<s>` indicates a sentence.

Either can be numbered:

    <s n="002">A quiet wedding we had:</s>

In this instance, the line numbering of 2 is an attribute of the sentence element "A quiet wedding we had:".
