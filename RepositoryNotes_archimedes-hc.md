Last updated 10/16/13

Search for '.?' for questions and '.!' for things that need to be fixed.

Quicklinks:

- [Digital Photography of Manuscripts]()
- [Transcribed Material]()
- [Indexed Material]()
- [Captured Material]()
- [Collected Material]()

## Digital Photography of Manuscripts

The collections of photography used by the project.  Thanks go to the Archimedes Project and e-codices for making the images available.

### Archimedes Palimpsest images

Example URNs:

    urn:cite:ap:apimg.027r-022v_Arch01r_Sinar_pseudo_no-veil
    urn:cite:ap:apimg.027r-022v_Arch01r_Sinar_pseudo_sharpie
    urn:cite:ap:aping.027r-022v_Arch01r_Sinar_true_pack8
    urn:cite:ap:apimg.0000-088v_Arch03r_Heiberg_ultraviolet_stitch
    urn:cite:ap:apimg.0000-088v_Arch03r_Heiberg_visible_stitch
    urn:cite:ap:apimg.cambridge_recto_white_registered
    urn:cite:ap:apimg.cambridge_recto_uv_registered

These images are available under the terms of the Creative Commons Attribution 3.0 Unported Access license (CC BY 3.0).

### Codex Bodmer 8 images

Example URN:

    urn:cite:ecod:codbod8.cb-0008_001r

These images are available under the terms of a Creative Commons license (CC BY-NC 3.0).  Any reuse must include the following attribution: Cologny, Fondation Martin Bodmer, Cod. Bodmer 8, f. 1r (www.e-codices.unifr.ch).

## Transcribed Material

Creating machine-actionable copies of written material.  These transcriptions are digital and diplomatic.

### Text

    archimedes-hc/texts/editions/cb8/Eutocius-Measurement-Circle-cb8.xml
    archimedes-hc/texts/editions/cb8/Eutocius-SC-cb8.xml
    archimedes-hc/texts/editions/cb8/Measurement-Circle-cb8.xml
    archimedes-hc/texts/editions/cb8/SphereandCylinder-cb8.xml

    archimedes-hc/texts/editions/heath/ .xml

    archimedes-hc/texts/editions/palimpsest/FloatingBodies-p5.xml
    archimedes-hc/texts/editions/palimpsest/Measurement-Circle-p5.xml
    archimedes-hc/texts/editions/palimpsest/SphereandCylinder-ap-1.xml

These are TEI-compliant XML texts and they have been annotated to mark their structure and to mark features of interest.  Structurally, the markup records what text appears on which folio.  It also splits the text into sections: books, prefaces, propositions, lemmata, etc.  The presence of figures is noted in XML tags.  In the Archimedes Palimpsest, the markup additionally records the text composing individual lines.<sup>[1]</sup>

XML markup expands abbreviations, acknowledges uncertain or lost text, and links words spanning two lines.  It is also used to capture features of interest, identifying personal names, place names, numbers, and labels of figures.  Work from 2012 included copious annotation on the labels; this was replaced with simpler markup in later work.

[1]: # "Note markup differences between 2012 and 2013 summer work."

### .? Diagrams
Should we transcribe the diagrams?  (I think yes.)  As they are currently captured, they are obscured and hard-to-see images which would be difficult to incorporate into manipulable data sets.  Diagram Markup Language is a possibility (and would also encode the logic of the diagrams).

## Indexed Material

Where RDF comes into play.  Much more structural (and in some cases, presentational).  Captured and collected material might also be considered subgroups of indexed material.

### Folios to sequence data

    archimedes-hc/collections/CodBod8_Pages.csv
    archimedes-hc/collections/EuchologionModelWithLabels.csv
    archimedes-hc/collections/palimpsestModel.csv

.? Verb used is presently undefined within the repository.

In linking a page with data on its sequence, these tables would need a one-way verb, perhaps `hasSequence`.

URNs which appear in these tables include folio URNs such as `urn:cite:ap:bod8.1r`, `urn:cite:fuhc:euch.1r`, and `urn:cite:fuhc:pal.1r`.

### Euchologion folios to bifolios

    archimedes-hc/collections/EuchologionModelWithLabels.csv

.? Verb used is presently undefined within the repository.

A suitable verb might be `hasBifolio`, which would work both ways.  This table includes data on what page each page is bifolios with in the Archimedes Palimpsest.

URNs appearing in this table are Euchologion folio URNs such as `urn:cite:fuhc:euch.1r`.

### Folios to recto/verso

    archimedes-hc/collections/EuchologionModelWithLabels.csv

.! Currently present only for the Euchologion.  

.? Is it necessary to have a separate index acknowledging this relationship, or is recto and verso implicit in the names of the folios with 'r' and 'v'?

.? Verb used is presently undefined within the repository.

In linking a page with data on whether it is recto or verso, the table would need a one-way verb, perhaps `rectoVerso`.

URNs appearing in this table are Euchologion folio URNs such as `urn:cite:fuhc:euch.1r`.

### Images of folios to folios

    archimedes-hc/indices/folioToImage.csv
    archimedes-hc/indices/imgToPalimpsest.csv
    archimedes-hc/indices/trueimgToPalimpsest.csv

The verbs for this index are `cite:illustrates` and `cite:illustratedBy`.  These link folios with the images illustrating them.

The URNs appearing in these tables include folio URNs such as `urn:cite:ap:bod8.1r` and `urn:cite:fuhc:pal.1r`, and folio image URNs such as `urn:cite:ecod:codbod8.cb-0008_001r` and `urn:cite:ap:apimg.027r-022v_Arch01r_Sinar_pseudo_no-veil`.

### Folios to default images

    archimedes-hc/indices/defaultImage.csv

.! Currently available only for Codex Bodmer 8.

The verbs for this index are `hmt:hasDefaultImage` and `hmt:isDefaultImage`.  These define the default image choice when navigating a digital edition of the manuscript.

The URNs appearing in this table include folio URNs such as `urn:cite:ap:bod8.1r` and folio image URNs such as `urn:cite:ecod:codbod8.cb-0008_001r`.

### Archimedes folios to Euchologion folios

    archimedes-hc/indices/archimedesToEuchologion.csv

.! Currently missing Cambridge folios (59r, 59v).

.! Presently available only for Archimedes folios, ignoring the other palimpsested texts and offering an incomplete Euchologion model.

.? The project focuses on Archimedes, but for the sake of a complete Euchologion model would it be good to include the other palimpsested texts?

The verbs for this index are `pal:isReusedBy` and `pal:reuses`.  These link Archimedes folios to Euchologion folios.

The URNs appearing in this table include folio URNs such as `urn:cite:fuhc:pal.1r` and `urn:cite:fuhc:euch.022v`.

### Archimedes sections to Eutocius sections

    archimedes-hc/indices/archimedesPassage-eutociusPassage.csv

The verbs for this index are `hmt:commentsOn` and `hmt:isCommentedOnBy`.  This table links sections of text in Archimedes to the sections discussing them in Eutocius's commentary.

The URNs appearing in this table include text section URNs such as `urn:cts:greekLit:tlg4072.tlg001.cb8:1.axioms.1` (Eutocius) and `urn:cts:greekLit:tlg0552.tlg001.cb8:1.axioms.2` (Archimedes).

.? Current layout suggests that the CodBod8 Eutocius text only comments on the CodBod8 Archimedes text and provides no link between Eutocius commentary and ArchPal text.  When we have a text and its commentary in the same manuscript, how is the link made?  Do we want to link commentary to text outside of manuscripts, or do we want to say that *this* copy of the commentary comments on *this* copy of the text?  If we have a text and its commentary in different manuscripts, would we still use `hmt:commentsOn`?  How does HMT handle this link?<sup>[2]</sup>

[2]: # "HMT has a tricky mix: scholia on the Iliad in general and scholia on particular variations in particular texts."

### .? Diagrams to sections

Is it necessary to create an index linking diagrams to the sections they appear in, or can we consider this implicit in the text XML?  (I think it's implicit, but do we have vocab for the arc/verb linking the two?)

## Captured Material

Citations using the Image Citation Tool.  These serve as indices, linking two points in RDF (often a URN for the feature and a URN for the region of interest (ROI) on the image).

### Paleography (paleographic observation to ROI)

    archimedes-hc/collections/CodBod8_paleo.csv

.? Verb used is presently undefined within the repository.

.! Consider DigiPal project for useful terminology.

.! Repository currently includes only a start on CodBod8 paleo.

### Diagrams (diagram to ROI)

    archimedes-hc/collections/ArchPal_diagramInventory.xml
    archimedes-hc/collections/CodBod8_EutociusFigures.csv
    archimedes-hc/collections/CodBod8_figures.csv

.? Verb used is presently undefined within the repository.

Possible verbs could be `cite:illustrates` and `cite:illustratedBy`.

The URNs appearing in these tables include diagram URNs such as `urn:cts:greekLit:tlg0552.tlg008:1.1.1`, `urn:cite:ap:efigures.01`, and `urn:cite:ap:figures.001`, as well as ROI URNs such as `urn:cite:ap:apimg.081v-088r_Arch03v_Sinar_pseudo_no-veil@0.11966667,0.5295,0.26666667,0.1545`, `urn:cite:ecod:codbod8.cb-0008_167v@0.3664,0.5641,0.6036,0.3976`, `urn:cite:ecod:codbod8.cb-0008_003r@0.3864,0.5401,0.2362,0.1643`.

.? Why the different figure URNs between summer 2012 and 2013?  Should these be changed?

### Textual sections (section to ROI)

    archimedes-hc/indices/archimedesToImage.csv
    archimedes-hc/indices/ArchPal_ArchimedesToImage-1.csv
    archimedes-hc/indices/ArchPal_ArchimedesToImage-2.csv
    archimedes-hc/indices/eutociusToImage.csv

The verbs for these indices are `cite:illustrates` and `cite:illustratedBy`.  These tables link sections of text to the ROIs that capture them in the photographed manuscript.

The URNs appearing in these tables include text section URNs such as `urn:cts:greekLit:tlg0552.tlg001.cb8:1.preface`, `urn:cts:greekLit:tlg0552.tlg001.ap:1.preface`, and `urn:cts:greekLit:tlg4072.tlg001.cb8:1.axioms.7`, as well as ROI URNs such as `urn:cite:ecod:codbod8.cb-0008_002r@0.0901,0.1148,0.5716,0.1583`,  and `urn:cite:ap:apimg.109r-106v_Arch45r_Sinar_pseudo_no-veil@0.4144,0.3196,0.3554,0.5169`.

### Miscellaneous material (misc to ROI)

    archimedes-hc/collections/ArchPal_misc.csv
    archimedes-hc/collections/ArchPal_nums.csv
    archimedes-hc/collections/CodBod8_graphics.csv
    archimedes-hc/collections/CodBod8_graphics-Eutocius.csv
    archimedes-hc/collections/CodBod8_graphics-SandC.csv

.? Verb used is presently undefined within the repository.

These tables link miscellaneous material (illuminated letters, decorative features, numerals, etc.) to the ROIs that capture them in the photographed manuscript.

Some tables link ROIs only to data, not URNs for the features.

.? Is it necessary to have URNs for features like marginal numerals, page numbers, decoration, etc?

.? Should some of this material (numerals, illuminated letters, and even features like '+'s) be transcribed?  Numerals were included in ArchPal XML texts -- also in CodBod8?  Illuminated letters are part of the text and so are already transcribed, but should they be marked up so that the XML text links to a illumination URN linked to a ROI?

The URNs appearing in these tables include ROI URNs and graphic URNs such as `urn:cite:ap:graphics.001` and `urn:cite:ap:egraphics.001`.

Some tables also link miscellaneous material to the section it is attached to.

## Collected Material

Collected material of interest, usually textual.  These can serve as indices, linking two points in RDF.  These are not structural unlike other indices and are more useful for research purposes.

### Personal names (name URN to description)

    archimedes-hc/collections/ArchPal_personNames.csv
    archimedes-hc/collections/CodBod8_personNames.csv

.? Verb used is presently undefined within the repository.

These tables link personName URNs with descriptions (data).  In RDF they would require only a one-way verb.

The URNs appearing in these tables are personName URNs such as `urn:cite:ap:pers.pers1` and `urn:cite:ap:persName.01`.

.? Why the difference between summer 2012 and 2013 URNs?  Should this be resolved?

.? If each manuscript has its own list of personal names, should the URNs have names that better show `urn:cite:ap:pers.pers1` is ArchPal and `urn:cite:ap:persName.01` is CodBod8?

.? Should there be a separate index saying that `urn:cite:ap:pers.pers1` in ArchPal and `urn:cite:ap:persName.02` in CodBod8 are equivalent (both refer to Archimedes)?

### Place names (name URN to description / Pleiades ID)

    archimedes-hc/collections/ArchPal_placeNames.csv
    archimedes-hc/collections/CodBod8_placeNames.csv

.? Verb used is presently undefined within the repository.

These tables link placeName URNs with descriptions (data) and also Pleiades IDs.

The URNs appearing in these tables include placeName URNs such as `urn:cite:ap:place.place1` and `urn:cite:ap:placeName.01`, as well as Pleiades IDs such as `pleiades.stoa.org/places/462503`.

.? Why the difference between summer 2012 and 2013 URNs?  Should this be resolved?

.? If each manuscript has its own list of place names, should the URNs have names that better show `urn:cite:ap:place.place1` is ArchPal and `urn:cite:ap:placeName.01` is CodBod8?

.? Should the CodBod8 data also be linked to Pleiades IDs?

### Duplications (duplication URN to section / ROI)

    archimedes-hc/collections/CodBod8_duplications-Eutocius.csv
    archimedes-hc/collections/CodBod8_duplications-SandC.csv

.? Verb used is presently undefined within the repository.

### Lacunae / omissions (URN to section / ROI)

    archimedes-hc/collections/CodBod8_lacunae.csv
    archimedes-hc/collections/CodBod8_omissions-Eutocius.csv
    archimedes-hc/collections/CodBod8_omissions-SandC.csv

.? Verb used is presently undefined within the repository.

### Variants (one reading to another reading)

    archimedes-hc/indices/Variants with DEGH.csv
    archimedes-hc/indices/Variants with DEGH-filtered.csv
    archimedes-hc/indices/variants.csv

.? Verb used is presently undefined within the repository.