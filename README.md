### Regex to find common errors in plant lists

The following regular expressions may be used to find 'patterns' of common errors in the formatting of plant lists:

Pattern | Description | Regex
--------|-------------|------
`aA` | mixed-case | `([a-z][A-Z])`
`AA` | all uppercase | `[A-Z]{2,}`
`a1` or `1a` | letters and numbers mixed | `([a-z]\d\|\d[a-z])`
`1` or `123` | any numbers | `[0-9]{1,}`
`a` or `1` | single characters | `\b\w\b`
`i ii iv` | Roman numerals | `\b[ivxlcdm]{1,}\b`
`McA` or `MacA` | Scottish names | `\b(Mc\|Mac)[a-z]`
`o'D` or `d'O` | contraction apostrophe | `\b\w'\w`
 `üé` etc. | accents and diacriticals | `[^\x00-\x7F]`
` - ` not<br>`dens-canis` | hyphens outside of specific-epithets | `[\W]-[\W]`
`L.c.` | non-capped initials | `\b[a-z]\.`
`Blog's, Jones'` | possessive apostrophes (sing.) | `(\b's\|s\b')`
`␠abc` | leading spaces | `␠\b`
`abc␠` | trailing spaces | `\b␠`
`abc␠␠def` | multiple whitespace | `[ ]{2,}`
