# Goals for Rendering Music Data

> Moving to a separate library ([Stravigor - Named for a rolling rastrum invented by famed composer Igor Stravinsky](https://github.com/colematthew4/Stravigor))

- *Easily transposable with musicxml schema*
- Can have multiple staves for different instruments or melodies
- Notes
  - must be selectable in the following contexts:
    - individually
    - multiplicative
    - across staves
  - must have the ability to contain these marking types:
    - [accidentials](https://en.wikipedia.org/wiki/Accidental_(music))
        (for special markings, e.g double flats/sharps, naturals quarter tones, etc)
    - [articulations](https://en.wikipedia.org/wiki/List_of_musical_symbols#Articulation_marks)
        (staccato, spiccato, accent, tenuto, marcato, fermata)
    - [ornaments](https://en.wikipedia.org/wiki/List_of_musical_symbols#Ornaments)
        (trill, mordent, turn, apoggiatuea, acciaccatura)
    - other instrument-specific notations (pizzicato, harmonics, directional bowing for strings,
        pedal marks for piano, mallet numbers for percussion, etc)
- Stave, measure, and note information is independent of each other
  - cross-note markings like ties, slurs, glissando, tuplets, octave signs, repeats should be
    stored separately from the notes themselves to help with garbage collection and memory
    optimization
  - All markings should have anchors on notes (e.g. dynamics)
- Allow custom text markers
