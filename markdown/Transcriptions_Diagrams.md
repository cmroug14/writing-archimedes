## Transcribing Diagrams

### An Introduction

While editors and philologists have spilled much ink in consideration of text - reconstructing the original text produced by the author, or transcribing that preserved in certain manuscripts - scholars have dedicated less study to  mathematical or scientific figures.  But the texts of Archimedes which lay out his argument are almost always accompanied by the mathematical diagrams which they construct.  Diagrams are a key element of Archimedes' writing, though they are often lost in the transmission of those works.

As the Holy Cross editions of *Sphere and Cylinder* are digital and diplomatic ones, we aimed to approach diagrams in a way analogous to how we approach texts.  We do this for two reasons: to make the diagram more legible when the manuscript is faded, damaged, or otherwise obscured, and to make the data encoded by the diagram machine-actionable.

### A 'Diplomatic' Diagram

**Diplomatic Edition**: "An edition exactly reproducing an original version. Diplomatic in this sense is recorded from the late 18th century, and is probably due to the publication of the Codex Juris Gentium Diplomaticus (1695), a collection of public documents, many of which dealt with international affairs." ([Oxford Reference](http://www.oxfordreference.com/view/10.1093/oi/authority.20110803095720226))

Diplomatic texts reproduce precisely the text that is conveyed by their manuscript originals, including abbreviations, spelling and punctuation, deletions and additions, and other variations.  Where the source text is unclear or lost, the diplomatic text is usually marked to acknowledge this.  The editions produced by Holy Cross use XML to transcribe and annotate the text.

A 'diplomatic' diagram, therefore, should reproduce precisely the diagram that is conveyed by a specific manuscript.  Where a text is composed of letters, the diagram is composed of geometric shapes and identifying labels.  Between manuscripts, the reader finds variations and corrections in the same diagram.

+ Structure of texts :: construction of diagrams
  + We cannot see how the scribe made the diagrams (though perhaps we can say he constructed them rather than copied them)
  + Construction of the diagrams is taken from the text, not from the diagrams
+ Words, letters, punctuation in texts :: shapes, labels in diagrams
  + Each shape receives its own object ID to mark it as a separate 'character' in the diagram
+ Paleography, letterforms :: appearance of shapes, labels
  + When polygons are curved and parabolas are circular arcs
 
The comparison between transcribing texts and transcribing diagrams is illuminating, but not perfect.  While the logical structure of a text can be gleaned from the progression of the author's writing, read left-to-right, up-to-down, the same cannot be said for the logical structure of diagrams.  Their construction is laid out and their parts defined in the text; the sequence of their construction must therefore be reconstructed from the text.

Similarly, when transcribing the diagrams we do have some different goals than when transcribing text.  The XML texts, for instance, do not preserve the appearance of the letters themselves; they do not preserve the information that this text is written minuscule while that text is written majuscule, for instance.  Paleographic observations are redirected to paleographic notebooks.  In the case of diagrams, however, we are interested in their appearance.  We therefore choose to exactly trace the figure as the manuscript presents it.  For this reason, we refer to diagram transcriptions as tracings.

### Scalable Vector Graphics

...

#### Encoding the Logic of Diagrams

...

+ Geometric
+ Construction
+ Signposts

### 'Markup' for Diagrams

...