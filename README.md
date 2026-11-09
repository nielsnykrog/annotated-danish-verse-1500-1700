# Annotated Danish Verse 1500–1700

A small, hand-curated dataset of **18 Danish-language verse texts (1529–1674)**
annotated with **syllable stress and metrical scansion** — intended for training
and evaluating metrical scansion models on early modern Danish, and for close
study of period versification.

Each of the 1,805 verse lines carries a double annotation:

1. **Syllable boundary marks** (`*`) inside the verse text.
2. **Metrical pattern** after `@`: a string of `+` (stressed) and `-` (unstressed)
   positions, one symbol per syllable.

This is version **1.0.0** of the dataset (see [CITATION.cff](CITATION.cff)).
It written to train an automatic scansion model, as described in this article.
It approaches the scansion of pre-1600 irregular verse as a four-beat 'knittelvers'. This means that it attempts to find four stressed syllables in these lines, leaving the rest of the syllables unstressed.
Future versions may add texts or alternative annotation to irregular verse.

## Example

From `HansPoulsenResen_Salme46.txt`:

```
Den Gud somn er en Fa*der Blijd@-+-+-+-+
Med søn oc Aand til*li*ge/@-+-+-+-
Hand er vort Haab met fast til*lijd/@-+-+-+-
Oc styrck' det wi maa si*ge.@-+-+-+-
```

## File format

Each text is one UTF-8 plain-text file (LF line endings, no BOM) with a metadata
header, a `###` separator, and the annotated verse body:

```
AUTHOR: <author name, or "Ukendt" (unknown)>
TITLE: <title as given by the edition/source>
YEAR: <year of the edition used, or empty>
PLACE: <place of printing, or empty>
PUBLISHER: <printer/publisher, or empty>
PARATEXT: <optional: heading/incipit paratext from the source>
###
<annotated verse>
```

- **Header fields** are sometimes left blank. Metadata may be improved in future versions.

## The 18 texts

| # | File | Author | Title | Year | Place | Publisher |
|---|------|--------|-------|------|-------|-----------|
| 1 | `AndersArrebo_DronningAnnaCatherinesDød.txt` | Anders Arrebo | Dronning Anna Catharines Død | 1612 | København | Henrich Waldkirch |
| 2 | `AndersBording_ÆrisKnude.txt` | Anders Bording | Æris Knude/ Den Ædle oc Høyfornemme Mand Povel Tscherning… | 1664 | København | Jørgen Lamprecht |
| 3 | `HansChristensenSthen_NaarDuGaarUdafDitKammer.txt` | Hans Christensen Sthen | Naar du gaar vdaff dit Kammer | — | — | — |
| 4 | `HansChristensenSthen_Salme51.txt` | Hans Christensen Sthen | Salme 51 En Liden Vandrebog | 1588 | — | — |
| 5 | `HansPoulsenResen_Salme32.txt` | Hans Poulsen Resen | Salme 32 | 1612 | København | Salomon Sartor |
| 6 | `HansPoulsenResen_Salme46.txt` | Hans Poulsen Resen | Salme 46 | 1612 | København | Salomon Sartor |
| 7 | `HansPoulsenResen_Salme6.txt` | Hans Poulsen Resen | Salme 6 | — | — | — |
| 8 | `HieronymusJustesenRanch_SamsonsFengsell.txt` | Hieronymus Justesen Ranch | Samsons Fengsell, akt 1 scene 1 | 1600 | — | — |
| 9 | `JacobWorm_Horse-Mager.txt` | Jacob Worm | Horse-Mager | — | — | — |
| 10 | `MartinLuther_HvorGudhanersåfastenborg.txt` | Martin Luther | Hvor Gud han er så fast en borg | 1569 | København | Hans Thomissøn |
| 11 | `ThomasKingo_DendførsteMorgen-sang.txt` | Thomas Kingo | Dend første Morgen-sang | 1674 | — | — |
| 12 | `ThomasKingo_HrKarstenHansensAtkesAfskeedfraLøveHerridt.txt` | Thomas Kingo | Hr Karsten Hansens Atkes Afskeed fra Løve-Herridt | 1669 | — | — |
| 13 | `Ukendt_BagvendtVise.txt` | Ukendt | Bagvendt Vise | 1562 | — | Langebek |
| 14 | `Ukendt_Denvintererbortgangen.txt` | Ukendt | Den wynter ær bortt gangen (Hjertebogen) | 1555 | — | — |
| 15 | `Ukendt_HarpensKraft.txt` | Ukendt | Harpens Kraft | 1583 | — | KAREN BRAHE |
| 16 | `Ukendt_HenhosBabylonsflod.txt` | Ukendt | Hen hos Babylons flod | 1569 | København | Hans Thomissøn |
| 17 | `Ukendt_IJesunavnbegyndevi.txt` | Ukendt | I Jesu navn begynde vi | 1529 | Rostock | Ludwig Dietz |
| 18 | `Ukendt_NubedevidenHelligånd.txt` | Ukendt | Nu bede vi den Helligånd | 1569 | København | Hans Thomissøn |

Titles longer than 60 characters are truncated above; the full title stands in
each file's header. `Ukendt` = unknown author.

## Corpus statistics

- 18 texts, 1,805 annotated verse lines
- 141 distinct metrical patterns
- Line lengths from 3 to 15 positions
- Period: 1529–1674; genres: hymns/psalms, occasional poetry (wedding, funeral,
  name-day), drama (Ranch, act 1 scene 1), ballads and broadside verse

## Provenance and editorial notes

- Texts follow the orthography of the editions cited in each header; spelling
  is reproduced as found (e.g. `somn`, `wi`, `oc`), with the period distinction
  between `i`/`j` and `u`/`v` retained.
- `PUBLISHER: KAREN BRAHE` in `Ukendt_HarpensKraft.txt` refers to the manuscript
  source (Karen Brahe's folio), not a printing house.

## License

The dataset (all files in `texts/`, plus metadata files) is licensed under
[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) —
see [LICENSE](LICENSE).

## Citation

See [CITATION.cff](CITATION.cff). In brief:

> Niels Nykrog. 2026. *Annotated Danish Verse 1500–1700* (version 1.0.0).
> Dataset. CC BY 4.0. https://github.com/nielsnykrog/annotated-danish-verse-1500-1700
