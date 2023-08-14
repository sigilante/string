#   `/lib/string`

A string library for mortals.

`/lib/string` implements a set of userspace functions for string manipulation adopting
similar names to the Python string standard library.  Urbit `tape`s (all of the functions
are for `tape`s only) are not exactly Python strings, of course, so `.format()` and
f-strings and the like are not addressed here.

What we do have:

#   Utility Lists

##  `++alphabet`

26-letter Roman alphabet, upper case and lower case.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz"
```

#### Source

```hoon
^~  `tape`(weld (gulf 65 90) (gulf 97 122))
```

#### Produces

A tape.

##  `++alpha-digits`

26-letter Roman alphabet, upper case and lower case, plus ten decimal digits.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"
```

#### Source

```hoon
^~  `tape`(weld alphabet digits)
```

#### Produces

A tape.

##  `++alpha-lower`

26-letter Roman alphabet, lower case.

```hoon
"abcdefghijklmnopqrstuvwxyz"
```

#### Source

```hoon
^~  `tape`(slag 26 alphabet)
```

#### Produces

A tape.

##  `++alpha-upper`

26-letter Roman alphabet, lower case.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZ"
```

#### Source

```hoon
^~  `tape`(scag 26 alphabet)
```

#### Produces

A tape.

##  `++ascii`

All printable ASCII characters (not in ASCII order).

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789 !\"#$%&'()*+,-./:;<=>?@[\\]^_`\{|}~ \0a\09"
```

#### Source

```hoon
^~  `tape`:(weld alphabet digits punctuation whitespace)
```

#### Produces

A tape.

##  `++digits`


Ten decimal digits.

```hoon
"0123456789"
```

#### Source

```hoon
^~  `tape`(gulf 48 57)
```

#### Produces

A tape.

##  `++hexdigits`


Sixteen hexadecimal digits, upper case and lower case.

```hoon
"0123456789ABCDEFabcdef"
```

#### Source

```hoon
^~  `tape`:(weld digits (gulf 65 70) (gulf 97 102))
```

#### Produces

A tape.

##  `++octdigits`

Eight octal digits.

```hoon
"01234567"
```

#### Source

```hoon
^~  `tape`(gulf 48 55)
```

#### Produces

A tape.

##  `++punctuation`     `tape`:(weld (gulf 32 47) (gulf 58 64) (gulf 91 96) (gulf 123 126))

All printable ASCII characters (not in ASCII order).

```
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789 !\"#$%&'()*+,-./:;<=>?@[\\]^_`\{|}~ \0a\09"
```

#### Source

```hoon
^~  `tape`:(weld alphabet digits punctuation whitespace)
```

#### Produces

A tape.

##  `++whitespace`      `tape`:(weld " " ~['\0a'] ~['\09'])

All printable ASCII characters (not in ASCII order).

```
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789 !\"#$%&'()*+,-./:;<=>?@[\\]^_`\{|}~ \0a\09"
```

#### Source

```hoon
^~  `tape`:(weld alphabet digits punctuation whitespace)
```

#### Produces

A tape.

---

#   Utility Sets

##  `++set-alphabet`

26-letter Roman alphabet, upper case and lower case.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz"
```

#### Source

```hoon
^~  `tape`(weld (gulf 65 90) (gulf 97 122))
```

#### Produces

A `(set @tD)`.

##  `++set-alpha-digits`

26-letter Roman alphabet, upper case and lower case, plus ten decimal digits.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"
```

#### Source

```hoon
^~  `tape`(weld alphabet digits)
```

#### Produces

A `(set @tD)`.

##  `++set-alpha-lower`

26-letter Roman alphabet, lower case.

```hoon
"abcdefghijklmnopqrstuvwxyz"
```

#### Source

```hoon
^~  `tape`(slag 26 alphabet)
```

#### Produces

A `(set @tD)`.

##  `++set-alpha-upper`

26-letter Roman alphabet, lower case.

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZ"
```

#### Source

```hoon
^~  `tape`(scag 26 alphabet)
```

#### Produces

A `(set @tD)`.

##  `++set-ascii`

All printable ASCII characters (not in ASCII order).

```hoon
"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789 !\"#$%&'()*+,-./:;<=>?@[\\]^_`\{|}~ \0a\09"
```

#### Source

```hoon
^~  `tape`:(weld alphabet digits punctuation whitespace)
```

#### Produces

A `(set @tD)`.

##  `++set-digits`


Ten decimal digits.

```hoon
"0123456789"
```

#### Source

```hoon
^~  `tape`(gulf 48 57)
```

#### Produces

A `(set @tD)`.

##  `++set-hexdigits`


Sixteen hexadecimal digits, upper case and lower case.

```hoon
"0123456789ABCDEFabcdef"
```

#### Source

```hoon
^~  `tape`:(weld digits (gulf 65 70) (gulf 97 102))
```

#### Produces

A `(set @tD)`.

##  `++set-octdigits`

Eight octal digits.

```hoon
"01234567"
```

#### Source

```hoon
^~  `tape`(gulf 48 55)
```

#### Produces

A `(set @tD)`.

##  `++set-punctuation`

Standard ASCII punctuation characters.

```
"!\"#$%&'()*+,-./:;<=>?@[\\]^_`\{|}~"
```

#### Source

```hoon
^~  `tape`:(weld (gulf 33 47) (gulf 58 64) (gulf 91 96) (gulf 123 126))
```

#### Produces

A `(set @tD)`.

##  `++set-whitespace`

Standard ASCII whitespace characters (space, newline, horizontal tab).

```hoon
" \0a\09"
```

#### Source

```hoon
^~  `tape`:(weld " " ~['\0a'] ~['\09'])
```

#### Produces

A `(set @tD)`.

---

#   Comparison Functions

##  `++is-alnum`

Tests whether all characters in a tape are either ASCII alphabetic characters or decimal digits.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-alpha-digits)))
```

#### Produces

A loobean (`?`).

##  `++is-alpha`

Tests whether all characters in a tape are from the ASCII alphabet.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-alphabet)))
```

#### Produces

A loobean (`?`).

##  `++is-ascii`

Tests whether all characters in a tape are from the printable ASCII character set.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-ascii)))
```

#### Produces

A loobean (`?`).

##  `++is-knot`

Tests whether a tape is a valid `@ta` label.

#### Source

```hoon
|=(=tape ((sane %ta) (crip tape)))
```

#### Produces

A loobean (`?`).

##  `++is-decimal`

Tests whether all characters in a tape are ASCII decimal digits.

Alias for `++is-digit`.

#### Source

```hoon
is-digit
```

#### Produces

A loobean (`?`).

##  `++is-digit`

Tests whether all characters in a tape are ASCII decimal digits.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-digits)))
```

#### Produces

A loobean (`?`).

##  `++is-hex`

Tests whether all characters in a tape are ASCII hexadecimal digits (upper case and lower case).

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-hexdigits)))
```

#### Produces

A loobean (`?`).

##  `++is-lower`

Tests whether all characters in a tape are from the lower case ASCII alphabet.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-alpha-lower)))
```

#### Produces

A loobean (`?`).

##  `++is-numeric`

Tests whether all characters in a tape are ASCII decimal digits.

Alias for `++is-digit`.

#### Source

```hoon
is-digit
```

#### Produces

A loobean (`?`).

##  `++is-octal`

Tests whether all characters in a tape are ASCII octal digits.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-octdigits)))
```

#### Produces

A loobean (`?`).

##  `++is-space`

Tests whether all characters in a tape are ASCII whitespace characters.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-whitespace)))
```

#### Produces

A loobean (`?`).

##  `++is-ta`

Tests whether a tape is a valid `@ta` label.

#### Source

```hoon
is-knot
```

#### Produces

A loobean (`?`).

##  `++is-tas`

Tests whether a tape is a valid `@tas` label.

Alias for `++is-term`.

#### Source

```hoon
is-term
```

#### Produces

A loobean (`?`).

##  `++is-term`

Tests whether a tape is a valid `@tas` label.

#### Source

```hoon
|=(=tape ((sane %tas) (crip tape)))
```

#### Produces

A loobean (`?`).

##  `++is-title`

Tests whether a tape is title case.

#### Source

```hoon
|=(=tape =((title tape) tape))
```

#### Produces

A loobean (`?`).

##  `++is-uc`

Tests whether a tape is a valid `@uc` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%uc +>-<:p))
```

#### Produces

A loobean (`?`).

##  `++is-ud`

Tests whether a tape is a valid `@ud` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%ud +>-<:p))
```

#### Produces

A loobean (`?`).

##  `++is-ui`

Tests whether a tape is a valid `@ui` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%ui +>-<:p))
```

#### Produces

A loobean (`?`).

##  `++is-upper`

Tests whether all characters in a tape are from the upper case ASCII alphabet.

#### Source

```hoon
|=(=tape =(~ (~(dif in (~(gas in *(set @tD)) tape)) set-alpha-upper)))
```

#### Produces

A loobean (`?`).

##  `++is-uv`

Tests whether a tape is a valid `@uv` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%uv +>-<:p))
```

#### Produces

A loobean (`?`).

##  `++is-uw`

Tests whether a tape is a valid `@uw` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%uw +>-<:p))
```

#### Produces

A loobean (`?`).

##  `++is-ux`

Tests whether a tape is a valid `@ux` value.

#### Source

```hoon
|=  =tape
^-  ?
=/  p  (bisk:so [[1 1] tape])
&(=(+((lent tape)) +>+<+:p) =(%ux +>-<:p))
```

#### Produces

A loobean (`?`).

---

#   Search and Conversion Functions

##  `++capitalize`

Converts the first character of the string to upper case.

#### Source

```hoon
|=(=tape (weld (upper (scag 1 tape)) (slag 1 tape)))
```

#### Produces

A tape.

##  `++center`

Center the string among whitespace.

#### Source

```hoon
|=  [=tape wid=@ud]
^-  ^tape
?.  (gth wid (lent tape))  tape
=/  lof  (div (sub wid (lent tape)) 2)
=/  rof  (sub wid (add lof (lent tape)))
:(weld `^tape`(zing (reap lof " ")) tape `^tape`(zing (reap rof " ")))
```

#### Produces

A tape.

##  `++count`

Count the number of times a value occurs in a given string.

#### Source

```hoon
|=([nedl=tape hstk=tape] (lent (fand nedl hstk)))
```

#### Produces

An atom.

##  `++echo`

Repeat a tape as a tape (rather than as a `(list tape)`).

#### Source

```hoon
|=([=tape n=@ud] ^-(^tape (zing (reap n tape))))
```

#### Produces

A tape.

##  `++ends-with`

Tests whether a string ends with a given substring.

#### Source

```hoon
|=([=tape subs=tape] ^-(? =(subs (slag (lent subs) tape))))
```

#### Produces

A loobean (`?`).

##  `++find-all`

Produce the index of every match of a given search string in a string.

Alias for `++fand`.

#### Source

```hoon
fand
```

#### Produces

A `(list @)`.

##  `++grab`

Returns a character at the given index.

Differs from `++snag` in that it returns a tape, not a cord.

#### Source

```hoon
|=([n=@ud =tape] ^-(^tape ~[(snag n tape)]))
```

#### Produces

A tape.


##  `++link`

Joins a list of tapes by inserting a separator between each element.

#### Source

```hoon
|=  [sep=tape =(list tape)]
^-  tape
=/  res   (snag 0 list)
=/  list  (slag 1 list)
|-
?~  list  res
%=  $
  list  t.list
  res   :(weld res sep i.list)
==
```

#### Produces

A tape.

##  `++ljust`

Left-justifies a string within whitespace.

#### Source

```hoon
|=  [=tape wid=@ud]
^-  ^tape
?.  (gth wid (lent tape))  tape
=/  rof  (sub wid (lent tape))
(weld tape `^tape`(zing (reap rof " ")))
```

#### Produces

A tape.

##  `++lower`

Converts all characters in a tape to the lower case ASCII alphabet.

Alias for `++cass`.

#### Source

```hoon
cass
```

#### Produces

A tape.

##  `++lstrip`

Strips whitespace from the left-hand side of a tape.

#### Source

```hoon
|=  =tape
^-  ^tape
|-
?.  (is-space ~[(snag 0 tape)])
  tape
$(tape (slag 1 tape))
```

#### Produces

A tape.

##  `++partition`

Separates a tape into a leading element, the matched element, and a trailing element.

#### Source

```hoon
|=  [nedl=tape hstk=tape]
^-  [l=tape n=tape r=tape]
=/  l   (scag (need (find nedl hstk)) hstk)
=/  nr  (slag (need (find nedl hstk)) hstk)
=/  n   (scag (lent nedl) nr)
=/  r   (slag (lent nedl) nr)
[l=l n=n r=r]
```

#### Produces

A 3-tuple of tapes.

##  `++replace`

Replaces each instance of a given substring in a tape.

#### Source

```hoon
|=  [bit=tape bot=tape =tape]
^-  ^tape
|-
=/  off  (find bit tape)
?~  off  tape
=/  clr  (oust [(need off) (lent bit)] tape)
$(tape :(weld (scag (need off) clr) bot (slag (need off) clr)))
```

#### Produces

A tape.

##  `++rfind`

Locates a value within a string, starting from the right-hand side and searching to the left.

#### Source

```hoon
|=([seq=tape =tape] ?~((find seq (flop tape)) ~ `(dec (sub (lent tape) (need (find seq (flop tape)))))))
```

#### Produces

A `(unit @)`.

##  `++rjust`

Right-justifies a string within whitespace.

#### Source

```hoon
|=  [=tape wid=@ud]
^-  ^tape
?.  (gth wid (lent tape))  tape
=/  lof  (sub wid (lent tape))
(weld `^tape`(zing (reap lof " ")) tape)
```

#### Produces

A tape.

##  `++rstrip`

Strips whitespace from the right-hand side of a tape.

#### Source

```hoon
|=  =tape
^-  ^tape
|-
?.  (is-space ~[(snag 0 tape)])
  tape
$(tape (slag 1 tape))
```

#### Produces

A tape.

##  `++split`

Splits a tape into tokens at a given separator.  (The separator is not returned as a token in the list.)

#### Source

```hoon
|=  [sep=tape =tape]
^-  (list ^tape)
=|  res=(list ^tape)
|-
?~  tape  (flop res)
=/  off  (find sep tape)
?~  off  (flop [`^tape`tape `(list ^tape)`res])
%=  $
  res   [(scag `@ud`(need off) `^tape`tape) res]
  tape  (slag +(`@ud`(need off)) `^tape`tape)
==
```

#### Produces

A `(list tape)`.

##  `++starts-with`

Tests whether a string starts with a given substring.

#### Source

```hoon
|=([=tape subs=tape] ^-(? =(subs (scag (lent subs) tape))))
```

#### Produces

A loobean (`?`).

##  `++strip`

Strips whitespace from both ends of a tape.

#### Source

```hoon
|=(=tape (lstrip (rstrip tape)))
```

#### Produces

A tape.

##  `++title`

Converts a string to title case (first letter of each space-separated word is capitalized).

#### Source

```hoon
|=(=tape (link " " (turn (split " " (zing (turn tape (cork trip lower)))) capitalize)))
```

#### Produces

A tape.

##  `++upper`

Converts all characters in a tape to the upper case ASCII alphabet.

Alias for `++cuss`.

#### Source

```hoon
cuss
```

#### Produces

A tape.

##  `++zfill`

Tests whether all characters in a tape are from the upper case ASCII alphabet.

#### Source

```hoon
|=  [=tape wid=@ud]
^-  ^tape
?.  (gth wid (lent tape))  tape
=/  lof  (sub wid (lent tape))
(weld `^tape`(zing (reap lof "0")) tape)
```

#### Produces

A tape.
