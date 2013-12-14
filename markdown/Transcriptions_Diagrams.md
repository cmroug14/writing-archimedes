## Transcribing Diagrams

### An Introduction

While editors and philologists have spilled much ink in consideration of text - reconstructing the original text produced by the author, or transcribing that preserved in certain manuscripts - scholars have dedicated less study to  mathematical or scientific figures.  But the texts of Archimedes which lay out his argument are almost always accompanied by the mathematical diagrams which they construct.  Diagrams are a key element of Archimedes' writing, though they are often lost in the transmission of those works.

As the Holy Cross editions of *Sphere and Cylinder* are digital and diplomatic ones, we aimed to approach diagrams in a way analogous to how we approach texts.  We do this for two reasons: to make the diagram more legible when the manuscript is faded, damaged, or otherwise obscured, and to make the data encoded by the diagram machine-actionable.

### A 'Diplomatic' Diagram

Diplomatic texts reproduce precisely the text that is conveyed by their manuscript originals, including abbreviations, spelling and punctuation, deletions and additions, and other variations.  Where the source text is unclear or lost, the diplomatic text is usually marked to acknowledge this.  The editions produced by Holy Cross use XML to transcribe and annotate the text.

A 'diplomatic' diagram, therefore, should reproduce precisely the diagram that is conveyed by a specific manuscript.  Where a text is composed of letters, the diagram is composed of geometric shapes and identifying labels.  Between manuscripts, the reader finds variations and corrections in the same diagram.  Where the diagram in the manuscript is unclear or parts completely lost, the transcription should be marked to acknowledge this.
 
The comparison between transcribing texts and transcribing diagrams is illuminating, but not perfect.  While the logical structure of a text can be gleaned from the progression of the author's writing, read left-to-right, up-to-down, the same cannot be said for the logical structure of diagrams.  Texts are sequential, but diagrams are static.  Their construction,however, is laid out and their parts defined in the text; the sequence of their construction must therefore be reconstructed from the text.

Similarly, transcribing the diagrams possesses some different goals than transcribing text.  The XML texts, for instance, do not preserve the appearance of the letters themselves; they do not record the fact that this text is written minuscule while that text is written majuscule.  Paleographic observations are redirected to paleographic notebooks.  In the case of diagrams, however, appearance is important to how the diagram is read.  The Archimedes Project at Holy Cross therefore chooses to exactly trace the figure as the manuscript presents it: for this reason, this edition refers to diagram transcriptions as tracings.

### Scalable Vector Graphics

The diagram tracings included in Holy Cross's edition are SVG files, an XML-based vector image format.  The tracings incorporate data on the geometric shapes that make up the diagram, the labels that accompany them, and the sequence of the construction as described by the text.  Like the XML used for texts, these SVG files also include editorial annotations.

#### Geometry

One way to understand the structure of a diagram is by breaking it down into its component shapes.  The diplomatic diagram transcriptions therefore record the each geometric piece that makes up the figure.  In the SVG file, each geometric object is defined with a machine-readable `<path/>` element and given a unique identifier with the `inkscape:label` attribute.

The shape defined by the `<path/>` element is as exact a representation of the shape drawn in the manuscript as possible: it is a tracing produced from the digital images.  This requires very precisely-taken photos, since a picture taken from an angle or folio that is not laid out perfectly flat will result in a warped diagram tracing.  The digital photography of the Archimedes Palimpsest and Codex Bodmer 8 makes this edition's diagram tracings possible.

The `inkscape:label` attribute, besides providing a unique identifier, also records what kind of shape is drawn.  This is most clearly necessary in the case of polygons in *Sphere and Cylinder*: the scribes in both Codex C and Codex Bodmer 8 customarily drew polygons with curved sides rather than straight ones.  A computer, drawing the shape laid out in the `<path/>` element, would not recognize such a shape to be a polygon, so the shape is instead identified within the `inkscape:label` attribute.

The structure of the unique identifier is therefore `[shape][labels]`.  In the case of circle ΑΒΓ, for instance, the unique identifier would be `circleΑΒΓ`.  The standard used by this edition is to include all the labels the text uses for that particular shape and to arrange them in alphabetic order.

#### Labels

Labels serve as the markers that link text to diagram, and so the diplomatic transcription of the diagram must also include the labels alongside the geometric elements.  Labels are included in `<text/>` elements and are simply the appropriate Greek letter.

The labels that are included in the tracings are exactly the labels that appear on the diagram, despite any disagreements there might be between the labels of the diagram and the labels discussed in the text.  

#### Construction

With the appearance of the static diagram preserved through the tracing's geometric objects and labels as discussed above, a third part of the SVG file applies the structure of the construction from the text to the diagram.  This data is in addition to the diplomatic transcription of the diagram, since it looks beyond the figure to the text.

The construction that is laid out in a proposition is broken down into steps.  This information is included in the diagram tracing through the group element `<g/>`.  The geometric objects and labels that are set out in the first step of the construction are contained within a `<g/>` element with the attribute `inkscape:label="tracesteps01"`, those set out in the second step are within a group identified as `tracesteps02`, etc.  The steps of the construction provide an alternative framework through which to study the diagram.

#### Editorial Notes

The physical diagrams which the SVG files trace are not all perfect: some are faded, obscured, or partially lost.  Occasionally additions were made to diagrams or the scribe erred and corrected his mistake.  The diagram tracings therefore encode all of this information to provide as complete a picture as possible.

The `<desc\>` element, contained within the `<path/>` or `<text/>` element, includes editorial information.  A label might be `visible` or `unclear`.  A geometric object can be `visible`, `unclear`, or `reconstructed`.  When the object is absolutely certain (as it often is in Codex Bodmer 8), it is marked as `visible`.  The current state of Codex C means that diagrams are often obscured or partially lost.  A shape which is legible but visually faded or obscured in part receives the marker `unclear`: a line for which the two endpoints can be seen but not the middle, for example, would be marked as such.  A shape which is known to have existed in the manuscript but which is too illegible for a confident tracing would be marked as `reconstructed`.  A scenario where a quarter of a circumscribed polygon is faded and completely missing in parts would receive such a marker: unlike the case with the uncertain line, there is not enough information to be sure that the missing arcs of the polygon followed the specific path drawn.  

There are some cases of diagrams where scribal corrections are apparent.  Having drawn a line incorrectly, the scribe sometimes scrapes away the error and draws the correct line.  Such a scenario requires `sic` and `corr` markers.  The same is true for labels: corrections are encoded with `sic` and `corr`.  If an addition in the form of a geographic object or label is made, it is marked with `add`; similarly, deletions are marked with `del`.
