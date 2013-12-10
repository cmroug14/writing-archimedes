## The Architecture of Digital Editions

### The Photography

The Archimedes Project at Holy Cross uses high-resolution, digital photographs to create the editions.  These images were produced by earlier digitization efforts by the Archimedes team and e-codices.  The digital Archimedes Palimpsest was released online by the Archimedes team and made available under the terms of the Creative Commons Attribution 3.0 Unported Access license (CC BY 3.0).  Codex Bodmer 8 comes from the digital library at e-codices.  The images are available under the terms of a Creative Commons license (CC BY-NC 3.0). Any reuse must include the following attribution: Cologny, Fondation Martin Bodmer, Cod. Bodmer 8 (www.e-codices.unifr.ch).

The images themselves are large .tif files.  One can zoom in and take a closer look at the manuscripts than could be achieved with the naked eye.  In the case of the Archimedes Palimpsest, the images were produced with multispectral imaging designed to bring out the erased text.

The photography is included in the digital editions produced by Holy Cross since they provide the evidence for the transcriptions.  Material pulled from the images can illustrate both textual and non-textual features.  The Archimedes Project at Holy Cross gives each image a unique URN that can be cited to identify the image.

### Digital, Diplomatic, TEI-compliant XML Texts

Diplomatic transcriptions are a major component of Holy Cross's edition.  These texts are .xml files and they are annotated with TEI-compliant XML.  Markup provides a structural purpose such as identifying what text appears on what folio and breaking the text up into sections (preface, propositions, ect).  Markup also expands abbreviations and notes features of interest such as personal or place names and diagram labels.

Each treatise in Holy Cross's project possesses a unique URN; furthermore, each section of text is made citable with its own unique URN.

### Image Citations

In producing these editions researchers refer to the images of the manuscript, whether in locating text to transcribe or non-textual features to catalog.  It is therefore valuable to be able to cite specific locations in specific images, and for that the project uses the Homer Multitext's method of creating citations with image URNs.

The project combines an image's usual URN with a set of coordinates (obtained with a tool such as the [Image Citation Tool](http://beta.hpcc.uh.edu/tomcat/apcite/ict.html)) to refer to a specific rectangular region within a specific image.

Including image citations for the material in these digital editions allows, for example, the readers of a specific section of text to be directed to that text's location on one or multiple folios.  It can also allow for various analyses, such as automatically determining the average space left for a diagram and locating outliers.

### Resource Description Framework

Images, texts, image selections, and other data are all tied together with RDF.  RDF expresses the relationships between these materials in the form of triples: two nodes joined by an arc.  In the Archimedes Project, these nodes can be URNs or data, while the arc is a verb for how they relate to each other.

With RDF, a section of text with URN `urn:cts:greekLit:tlg0552.tlg001.ap:1.preface` can be linked to a location on an image given by the URN `urn:cite:ap:apimg.109r-106v_Arch45r_Sinar_pseudo_no-veil@0.4144,0.3196,0.3554,0.5169` with the verb `cite:illustratedBy`.  So the preface of *Sphere and Cylinder* in the Archimedes Palimpsest is illustrated by a region on the no-veil image of 45r.  When the nodes are both URNs the inverse of this statement can also be defined, where a region on the no-veil image of 45r `cite:illustrates` the preface of *Sphere and Cylinder* in the Archimedes Palimpsest.

RDF links materials in these digital editions beyond text and image.  The framework provides a way to state that diagrams are illustrated by particular images, that a folio in the Archimedes Palimpsest is also a folio in the Euchologion, that a section of Eutocius comments on a section of Archimedes, etc.

When RDF links a URN to data, there is no inverse verb. For example, to describe the sequence of folios one would say  the first folio of the Archimedes Palimpsest, `urn:cite:fuhc:pal.1r`, `hasSequence` `1`.  `1` is a piece of data, not a unique URN, and that same number might appear in a variety of other unrelated contexts.