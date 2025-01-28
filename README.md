# Copyright Year Updater
By Tyler Morgan.

## Overview
I've had a hard time finding a simple way to update copyright footers for my webpages. All of the solutions either collection data from the user and/or doesn't provide the copyright types I need. So I made my own that suits my needs. Maybe someone has created something similar, but it was not easy enough for me to find. So I'll contribute more code I guess!
## Goals
* Create a lightweight JavaScript file.
* Create both static and dynamic years and year ranges.
* Reduce reliance on `id` attributes.
* Reduce data collection when retrieving the year for users.
* Minimal updating of the file (one string change per year).
* Simple syntax setting up copyright years.

## Year Types


### Dynamic Year
If you just want to update the year to the current year (e.g., _&copy; 2025 Tyler Morgan. All rights reserved._ or whatever), I gotcha covered.
#### Code
Add `data-copyright-currentyear` to any HTML tag. Preferably an empty `span`. You can leave the attribute value empty. Example: `<span data-copyright-currentyear></span>` will spit out "2025" (since the year is 2025 when I'm writing this).


### Static Year
If you just want to add the copyright year of a work, no updating needed. This would work. Of course, you can just manually add the year in the text content, up to you, whatever floats your boat.
#### Code
Add `data-copyright-year="YYYY"` to any HTML tag. Preferably an empty `span`. Change out "YYYY" to the year you want, obviously. Example: `<span data-copyright-year="1973"></span>` will spit out "1973".


### Dynamic Year Range
If you're looking to add a year range that updates the ending number to the current year (eg., _&copy; 2020-2025 Tyler Morgan. All rights reserved._), this is the one for you.
#### Code
Add both `data-copyright-year="YYYY"` and `data-copyright-endyear="currentyear"` to any HTML tag. Preferably an empty `span`. Change out "YYYY" to the year you want, but "currentyear" should be left as is. Example: `<span data-copyright-year="2004" data-copyright-endyear="currentyear"></span>` will spit out "2004-2025". If you change out "currentyear" to "currentyear2", it will display the last two digits of the current year. Example: "2020-25".


### Static Year Range
You just want an unchanging year range? Cool, I got that too.
#### Code
Add both `data-copyright-year="YYYY"` and `data-copyright-endyear="YYYY"` to any HTML tag. Preferably an empty `span`. Change out "YYYY" to the year you want. Example: `<span data-copyright-year="1996" data-copyright-endyear="2013"></span>` will spit out "1996-2013".

## Little Tip
The `data-copyright-year` and `data-copyright-endyear` are string values if you need to add lettering to the years. If for whatever reason you need BC or AD, you can totally do so.
