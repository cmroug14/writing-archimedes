## Linking Digital Editions of Diagram and Text

The diagrams and text of Archimedes, where both exist in the manuscripts, must be understood together.  The works of the ancient mathematician become most legible when the text and diagrams are considered alongside each other: diagrams lose their meaning without the argument of the text, but the text's argument is incomplete without the diagrams.

This section describes the current standards of Holy Cross's edition as well as several planned standards and some proposals.  The later part of the section also considers various research options made possible by this edition.

### Digital Architecture

Fifteen diagrams exist alongside *Sphere and Cylinder* in Codex C; thirty-one exist in Codex Bodmer 8.  The remainder were never drawn into the spaces left for them.  In Holy Cross's edition, both diagrams and empty spaces possess URNs with the format `urn:cite:ap:apdiagrams.#` (Codex C) and `urn:cite:ap:figures.#` (Codex Bodmer 8).

The texts of *Sphere and Cylinder* are preserved in their entirety for both manuscripts.  These possess the URNs `urn:cts:greekLit:tlg0552.tlg001.ap` (Codex C) and `urn:cts:greekLit:tlg0552.tlg001.cb8` (Codex Bodmer 8).

In Holy Cross's edition, these diagrams and texts are represented in two ways: digital photography of the manuscripts themselves and digital diplomatic transcriptions.

Particular diagrams are linked to the section of text they accompany via a `<figure/>` element in the text transcription XML, and this relationship will be explicitly defined with RDF triples.  The relationship might be as follows: `urn:cite:ap:apdiagrams.#` `illustrates` `urn:cts:greekLit:tlg0552.tlg001.ap.1.propositions.#` and `urn:cts:greekLit:tlg0552.tlg001.ap.1.propositions.#` `isIllustratedBy` `urn:cite:ap:apdiagrams.#`.

The geometric objects discussed in the text and drawn in the diagram have two sets of labels that refer to them: the ones with which the text names them and the ones marking them in the figure.  Individual geometric objects are linked to the first set through their identifiers, which come from the labels used in the text (circle ΑΒΓ is `circleΑΒΓ`).  They will be linked to the second set via RDF triples so that a geometric object `hasLabel` Α, for example.

The steps of the construction recorded in the diagram tracings will also link to the text that lays those steps out.  Each step in the tracing has an identifier `tracesteps#`; RDF triples will link those steps with the appropriate section of text.  The verb could be something along the lines of text `constructs` a step of the tracing and that step of the tracing `isConstructedBy` text.  Alternatively, perhaps it would be appropriate to reuse `illustrates` and `isIllustratedBy`.

### Analyzing Diagram and Text

The architecture of the Archimedes Project at Holy Cross allows the analysis of the relation between diagrams and text in a number of ways.

#### Physical Relation on Manuscript Folios

The method used for citing the region of interest on a digital photograph where a diagram or section of text can be found provides a 'physical' location for each.  Additionally, the `<figure/>` element in the text XML records at what point in the progression of the text the diagram appears.

With such data, it is possible to investigate questions concerning where diagrams stood in relation to the text (even for spaces where diagrams were never drawn in).  Did they generally appear at the start of the text/near the construction/somewhere in the middle/at the end?  Do different manuscripts have different setups?  How often was text wrapped around diagrams rather than standing separately?

Should Holy Cross's digital edition of Archimedes be expanded in the future to include additional manuscripts, perhaps related to each other, it would be interesting to consider how (if at all) the layout of diagrams and text changed during the transmission of Archimedes.

#### Labels Preserved in Diagram and Text

The creation of diplomatic transcriptions of text and diagrams results in a record of the labels which appear in the text and those which appear in the diagram.  At the most basic level, these two records can be compared to see if the labels used in a certain proposition are the same as the labels used in its diagram.  The textual labels and diagram labels can also be compared for a particular geometric object.

By looking at the labels in the text XML and nearby words for context, a computer could automatically narrow down and perhaps determine which geometric object is being discussed at each point in the text.

These data sets allow the investigation of various questions about the labels of Archimedes.  Where do the labels of text and diagram disagree?  How many different ways does the text refer to the same geometric object?  Are there patterns in the arrangement of labels (ΑΒΓ vs ΓΒΑ) for the same geometric object?  How often are geometric objects fully labeled (ΑΒΓ vs ΑΒ)?  Even if all the same labels are used between the figure and the text, are they used for the same geometric objects, or do they disagree?

If data from additional manuscripts is collected in the future, it would be interesting to compare the transmission of labels in the diagrams and of those in the text.  

#### Construction of the Diagram

Incorporating the steps of the construction into the diagram tracing records in what order geometric objects are constructed.  It is possible to analyze this data to seek patterns within treatises: does Archimedes generally follow the same progression?  How do constructions most commonly begin?  Do constructions always increase in complexity with later propositions?