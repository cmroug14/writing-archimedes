## The Archimedes Project at Holy Cross, 2013-14

We will create editions of Archimedes' *On the Sphere and Cylinder* in Codex C (10th century) and Codex Bodmer 8 (16th century), as well as an edition of Eutocius's Commentary on *Sphere and Cylinder* preserved in Codex Bodmer 8.

### The Manuscripts

#### Codex C

[aka the Archimedes Palimpsest]

#### Codex Bodmer 8

[...]

### Our Editions

At Holy Cross, we will create editions that are diplomatic, digital, complete, and open.

#### Diplomatic

The Archimedes Project at Holy Cross will produce diplomatic transcriptions of *Sphere and Cylinder* as written in Codex C and preserved today in the Archimedes Palimpsest, *Sphere and Cylinder* as preserved in Codex Bodmer 8, and Commentary on *Sphere and Cylinder* as preserved in Codex Bodmer 8.

Diplomatic is a term which is familiar from print editions.  It has different goals from a critical edition: where a critical edition seeks to publish the 'best' text (usually the 'original' text as written by its author), a diplomatic edition seeks to publish a transcription of precisely what a single manuscript contains.  This includes material ranging from lengthy alternate readings to differences in punctuation or accentuation.

Diplomatic editions can serve as a way to become familiar with the material in a manuscript even if the manuscript itself is inaccessible. 

#### Digital

The project's transcriptions will be digital: they will be machine-readable and machine-actionable Greek.  The project uses TEI-compliant XML to transcribe and annotate the text.  The Text Encoding Initiative's standards allow the text to be marked up semantically.

Digital editions create datasets out of these texts.  For instance, the Archimedes Project at Holy Cross is examining *Sphere and Cylinder* in two manuscripts: digital, diplomatic texts allow for automatic comparison between the two.

A digital format possesses several advantages in the creation of a diplomatic edition.  Firstly, it takes advantage of the past initiatives to digitize the Archimedes Palimpsest and Codex Bodmer 8.  High resolution digital photographs are online, licensed to be freely accessible and reusable.  Holy Cross's digital editions can link to those images or include them alongside their texts so that the evidence for the diplomatic transcriptions is available to the reader.

Secondly, a digital format allows more freedom to encode and represent the structure of the text.  Data such as the fact that a certain stretch of text appears on a certain folio, or that certain folios compose a certain quire, can all be encoded in the digital edition.  This data can be incorporated into a website, for instance, where the reader might choose between navigating the text by physical folio or doing so by section of text.

Thirdly, a digital format offers methods to represent the links between texts.  This is valuable when considering the Commentary on *Sphere and Cylinder* alongside the treatise itself.  Certain sections of Eutocius's commentary comment on specific sections of the Archimedes text.  These links can be encoded in the digital edition; in a website presenting the digital edition, the reader can be linked directly to connected material.

The digital nature of these editions also makes the below features of this project possible.

#### Complete

The Archimedes Project at Holy Cross uses the total editing approach of the Homer Multitext project.  This approach encompasses the project's goal of modeling the structure of the text, as discussed above.  Furthermore, this goes beyond stating that a certain stretch of text appears on a certain folio: the Archimedes Project cites the location on a folio that a section of text appears on.  This is useful especially in the Archimedes Palimpsest, where the heavily-obscured text appears in two columns on each folio.

The total editing approach also allows features beyond the text to be included in a complete edition.  The most notable example in Archimedes and Eutocius are the diagrams: an image of each diagram (or space left for one that was never drawn in) is captured, and its location on the folio cited.  The same holds true for other marks on the folio, including illuminated letters starting certain sections, marginal numerals numbering each proposition, and symbols appearing on certain lines.

#### Open

The Archimedes Project at Holy Cross intends to create editions that are accessible with data that is reusable.  The digital format makes this possible: the editions can be put online, reachable by anyone with an internet connection.  The data (texts, images, etc.) can be downloaded and manipulated by anyone interested.  Just as online images made the Archimedes Palimpsest and Codex Bodmer 8 accessible, the Archimedes Project must make its data and edition freely accessible and freely reusable.  The editions and scholarship produced by the project must not be hidden behind a paywall, but rather be open data.  By making the data available and freely licensed, the Archimedes Project will encourage further scholarship.

### The Architecture of Digital Editions

#### The Photography

The Archimedes Project at Holy Cross uses high-resolution, digital photographs to create the editions.  These images were produced by earlier digitization efforts by the Archimedes team and e-codices.  The digital Archimedes Palimpsest was released online by the Archimedes team and made available under the terms of the Creative Commons Attribution 3.0 Unported Access license (CC BY 3.0).  Codex Bodmer 8 comes from the digital library at e-codices.  The images are available under the terms of a Creative Commons license (CC BY-NC 3.0). Any reuse must include the following attribution: Cologny, Fondation Martin Bodmer, Cod. Bodmer 8 (www.e-codices.unifr.ch).

The images themselves are large .tif files.  One can zoom in and take a closer look at the manuscripts than could be achieved with the naked eye.  In the case of the Archimedes Palimpsest, the images were produced with multispectral imaging designed to bring out the erased text.

The photography is included in the digital editions produced by Holy Cross since they provide the evidence for the transcriptions.  Material pulled from the images can illustrate both textual and non-textual features.  The Archimedes Project at Holy Cross gives each image a unique URN that can be cited to identify the image.

#### Digital, Diplomatic, TEI-compliant XML Texts

Diplomatic transcriptions are a major component of Holy Cross's edition.  These texts are .xml files and they are annotated with TEI-compliant XML.  Markup provides a structural purpose such as identifying what text appears on what folio and breaking the text up into sections (preface, propositions, ect).  Markup also expands abbreviations and notes features of interest such as personal or place names and diagram labels.

Each treatise in Holy Cross's project possesses a unique URN; furthermore, each section of text is made citable with its own unique URN.

#### Image Citations

In producing these editions researchers refer to the images of the manuscript, whether in locating text to transcribe or non-textual features to catalog.  It is therefore valuable to be able to cite specific locations in specific images, and for that the project uses the Homer Multitext's method of creating citations with image URNs.

The project combines an image's usual URN with a set of coordinates (obtained with a tool such as the [Image Citation Tool](http://beta.hpcc.uh.edu/tomcat/apcite/ict.html)) to refer to a specific rectangular region within a specific image.

Including image citations for the material in these digital editions allows, for example, the readers of a specific section of text to be directed to that text's location on one or multiple folios.  It can also allow for various analyses, such as automatically determining the average space left for a diagram and locating outliers.

#### Resource Description Framework

Images, texts, image selections, and other data are all tied together with RDF.  RDF expresses the relationships between these materials in the form of triples: two nodes joined by an arc.  In the Archimedes Project, these nodes can be URNs or data, while the arc is a verb for how they relate to each other.

With RDF, a section of text with URN `urn:cts:greekLit:tlg0552.tlg001.ap:1.preface` can be linked to a location on an image given by the URN `urn:cite:ap:apimg.109r-106v_Arch45r_Sinar_pseudo_no-veil@0.4144,0.3196,0.3554,0.5169` with the verb `cite:illustratedBy`.  So the preface of *Sphere and Cylinder* in the Archimedes Palimpsest is illustrated by a region on the no-veil image of 45r.  When the nodes are both URNs the inverse of this statement can also be defined, where a region on the no-veil image of 45r `cite:illustrates` the preface of *Sphere and Cylinder* in the Archimedes Palimpsest.

RDF links materials in these digital editions beyond text and image.  The framework provides a way to state that diagrams are illustrated by particular images, that a folio in the Archimedes Palimpsest is also a folio in the Euchologion, that a section of Eutocius comments on a section of Archimedes, etc.

When RDF links a URN to data, there is no inverse verb. For example, to describe the sequence of folios one would say  the first folio of the Archimedes Palimpsest, `urn:cite:fuhc:pal.1r`, `hasSequence` `1`.  `1` is a piece of data, not a unique URN, and that same number might appear in a variety of other unrelated contexts.