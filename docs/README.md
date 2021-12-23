enstwist
========

This is a backwards-compatible fork of the popular dnstwist program, with a few added features:
 - the ability to lookup the address and owner of an ENS name
 - the ability to use a larger set of glyphs
 - the ability to perform a reverse lookup
 - the ability to toggle IDNA(punycode)

--ens
ENS names are open to similar glyph-related problems that DNS names are. This option will lookup the address and owner for each name. Requires 'WEB3_PROVIDER_URI' environment variable. This option also uses a different set of glyphs (based on https://www.irongeek.com/homoglyph-attack-generator.php) than the regular dnstwist usage, which - per the dnstwist README - targets ranges "of Unicode characters to ensure that generated domains can be registered in practice." The Ethereum Name Service, however, has far fewer (if any) restrictions on mixing character sets when registering a name. 

--extended-glyphs
You are able to use a combined set of the regular glyphs and the --ens glyphs with this argument.

--reverse-lookup
For regular dnstwist usage, does a PTR lookup. For --ens usage, get the reverse name.

--toggle-idna
Toggle the default IDNA behavior. For list, json, and csv formats, decode the name (and optional reverse lookup). For cli format, encode the name (and optional reverse lookup). This is helpful when inspecting --ens reverse names in cli mode, as you can more easily differentiate homoglyphs which may render the same in a terminal.

![Demo](/docs/demo.gif)
