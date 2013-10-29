# On Digital 'Diplomatic' Transcriptions of Diagrams

Focusing primarily on the diagrams of the Archimedes Palimpsest (since they would gain much in terms of sheer accessibility through transcriptions), but also possible for the diagrams of Codex Bodmer 8.

## Why?

For comparison, why do we transcribe the text of a manuscript?  Digitally, diplomatically transcribing the text of a manuscript accomplishes certain goals.

+ Makes the text in the manuscript more accessible to those unfamiliar with the manuscript's paleography
+ Makes the text in the manuscript more accessible when it is faded / obscured
+ Makes the text in the manuscript machine-actionable (allows automatic comparison with another manuscript's diplomatic transcription, for instance)
+ Allows for annotations to mark certain features (personal names, unclear text, expanded abbreviations, etc.)


### Why Transcribe Diagrams?

Initial reasons to transcribe diagrams can be gleaned from comparison with textual transcriptions.  Diagram transcriptions would have these goals in common:

+ Makes the diagram in the manuscript more accessible when the manuscript figure is faded/ obscured
+ Makes the diagram in the manuscript machine-actionable (allows automatic comparison with another manuscript's transcription, for instance)
+ Allows for annotations to mark certain features (labels, circles, unclear lines)?

## 'Diplomatic' Transcription?

What would it mean to 'diplomatically' transcribe diagrams as they appear in a manuscript?  In text, a diplomatic transcription reproduces the text exactly as it appears in the manuscript.  (Although this brief definition might not be perfectly apt: our transcriptions do not reproduce the hand of the manuscript -- where there is a shift from minuscule to majuscule for instance, our transcription does not acknowledge it.  Our transcriptions capitalize names where capitalization is not present in the manuscript, and they do not transcribe iota subscripts as superscript as they appear in the manuscript.)

For diagrams, they would only be transcribed where they are actually present in the manuscript: there are many diagrams which were never drawn in.  A 'diplomatic' transcription of a diagram would represent the diagram exactly as it appears in the manuscript.  This means creating a reproduction that looks like the representation in the manuscript: if tangent lines are actually drawn as curves, they would be reproduced as such.  Something like a tracing of the manuscript would accomplish this.  The reproduced diagram should be proportional to the diagram as it appears in the manuscript.

Other elements to consider include the problem of unclear or lost parts of the diagram.  TEI-compliant XML handles this problem for text, but there is not a similar method for diagrams.  Should the transcription be annotated to reflect 'this is an unclear line' or 'this is an unclear label'?  How could this best be accomplished?

## How?

We definitely do want to use vector images for whatever is produced.

+ [Diagram Markup Language](http://episteme.sourceforge.net/dml.html) encodes the logic of the diagrams and extends the ePix graphics library to construct the presentation of the diagrams
    + produces a .svg file
+ Could use an graphics editor to draw circles, lines, and overlay these on the manuscript image to essentially trace the diagram by hand
    + we would want to trace the geometric elements of the diagram (circles, lines, etc.) but not necessarily the labels, since labels are text
        + separate .xml file for labels? (like the separate file for scholia? and linked to a specific region through an image ROI like scholia?) again, this might be getting too complicated
    + ~~Is Gimp good for editing vectors?~~ Gimp doesn't work well and can't create .svg files: use [Inkscape](http://inkscape.org/) perhaps
    + produce a .svg file?
+ Could overlay a coordinate axis on the image, pick out significant points (two points could describe a line; three points could describe a circle, an arc, a triangle; etc.) and then mathematically describe each geometric piece on the coordinate axis
    + program could then take these equations and graph them or perhaps produce an image in .svg format?

The transcriptions can either take the form of one image for the whole diagram or multiple images for each part (circle ΑΒΓΔ, line ΓΔ, etc.) and a final stacked image for the whole diagram.  Are there reasons we might want separate parts?

+ Analyzing complexity of a diagram
+ Comparing diagrams in different manuscripts by each part
+ Saying 'this section' is unclear but 'that section' is clear
+ Analyzing what parts most commonly appear (like circle ΑΒΓΔ)
