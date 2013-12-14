## TEI-compliant XML Texts

### An Introduction

The diplomatic transcription of a text can serve several purposes.  Firstly, it makes the text more accessible: transcriptions can aid a reader unfamiliar with the paleography of a manuscript or one struggling with heavily obscured or damaged text, such as in the Archimedes Palimpsest.  Secondly, digital diplomatic transcriptions make the texts of manuscripts into machine-actionable data, allowing computers to tackle the task of locating variations of words currently unaccounted for in dictionaries, comparing the texts preserved in two different manuscripts, or determining how often a particular word is abbreviated rather than spelled out.

In order to accomplish this second goal more fully, texts are marked up semantically so that a computer might understand that this stretch of text was deleted in the manuscript or that word was abbreviated.  Transcriptions are in XML format, so this and other information is included in tagged annotations.  The [Text Encoding Initiative](http://www.tei-c.org/index.xml) has developed and maintains the standard for semantic, digital texts.

### Diplomatic Texts

**Diplomatic Edition**: "An edition exactly reproducing an original version. Diplomatic in this sense is recorded from the late 18th century, and is probably due to the publication of the Codex Juris Gentium Diplomaticus (1695), a collection of public documents, many of which dealt with international affairs." ([Oxford Reference](http://www.oxfordreference.com/view/10.1093/oi/authority.20110803095720226))

The marked-up transcriptions in this edition diplomatically reproduce a great deal of information that is contained within the manuscript.  Material preserved in Holy Cross's edition includes the following:

+ Spelling
+ Punctuation
+ Additions
+ Deletions
+ Corrections
+ Abbreviations
+ Variations

The text of the manuscript includes a great deal of information which could be noted, some beyond the bounds of the project at Holy Cross.  Material which is present in the digital photography but which does not receive note in the XML transcription includes the following:

+ Scribal hands
+ Ligatures
+ Iota Adscripts
+ Proper nouns lacking capitalization
+ Illuminated letters
+ Different colored inks

### TEI Markup

The following is a description of tags used in Holy Cross's edition of Archimedes.

#### Diplomatic Annotations

+ `<add/>`: additions
+ `<del/>`: deletions
+ `<sic/>`: text corrected by the scribe (used alongside `<corr/>`)
+ `<corr/>`: the correction by the scribe (used alongside `<sic/>`)
+ `<abbr/>`: the letters of an abbreviation present in the manuscript (used alongside `<expan/`>)
+ `<expan/>`: the expanded, full word of the abbreviation (used alongside `<abbr/>`)
+ `<gap/>`: gaps

#### Editorial Annotations

+ `<unclear/>`: unclear text
+ `<supplied reason="lost"/>`: lost text
+ `<persName/>`: personal names
+ `<placeName/>`: place names
+ `<w/>`: marks a word when separated across two lines

#### Mathematical Texts and TEI

As the works of Archimedes are mathematical ones, specific markup is necessary to handle the mathematical features of the text.  The Archimedes Project at Holy Cross uses the following:

+ `<rs/>`: diagram labels
+ `<num/>`: numerals
+ `<figure/>`: diagrams

#### The Structure of the Text

The Holy Cross edition mainly notes the positioning of text on folios via RDF and reference to regions of interest on the digital images.  However, XML markup allows for some notation on the structure of the text in addition to its content, and such markup is included in the Holy Cross edition.

The structure of the text takes two forms: the progression of the text as it is laid out in books, prefaces, axioms, lemmata, propositions, etc., and the location of the text as it is laid out on each folio.  The following tags are used:

+ `<div type="book"/>`: books of treatises
+ `<div type="section"/>`: shorter sections within treatises (e.g: preface, propositions, etc.)
+ `<seg type="line"/>`: lines of text (used for the Archimedes Palimpsest, not Codex Bodmer 8)
+ `<milestone/>`: marks the start of a new folio