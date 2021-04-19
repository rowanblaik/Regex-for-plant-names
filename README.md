### Regex for plant lists

The following regular expressions may be used to find errors, or words prone to error, in plant names:

Pattern | Description | Regex
--------|-------------|------
`aA` | irregular mixed-case | `([a-z][A-Z])`
`AA` | uppercase word | `[A-Z]{2,}`
`a1` or `1a` | letters and numbers mixed | `([a-z][0-9]\|[0-9][a-z])`
`1` or `123` | numbers | `[0-9]+`
`a` or `1` | single characters | `\b\w\b`
`i ii iv` | Roman numerals | `\b[ivxlcdm]+\b`
`McA` or `MacA` | Scottish names | `\b(Mc\|Mac)[a-z]+`
`o'D` or `d'O` | contraction apostrophe | `\w+'\w+`
 `üé` etc. | accents and diacriticals | `[^\x00-\x7F]`
`dens- canis` | irregular hyphenation | `[^a-z]-+\|-+[^a-z]`
`L.c.` | non-capped initials | `\b[a-z]\.`
`Blog's, Jones'` | possessive apostrophes | `(\b's\|s\b')`
`␠abc` | leading whitespace | `^[^\S\r\n]+`
`abc␠` | trailing whitespace | `[^\S\r\n]+$`
`abc␠␠def` | multiple whitespace | `[^\S\r\n]{2,}`
