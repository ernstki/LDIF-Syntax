# LDIF-Syntax

[LDAP Data Interchange Format][ldif] syntax highlighter and snippets for
[Sublime Text 3][st3].

Syntax highlighting and checking is done in conformance with the definitions of
[RFC 2849][rfc]. The syntax highlighter distinguishes between plain text and
base64-encoded attribute values. Within both types, invalid characters are
automatically highlighted.


## Snippets

This package contains snippets for the LDAP modify operations defined by RFC
2849. It also attempts to detect erroneous modify definitions and highlights
them as well.


## Use with [bat][]

See [the "Adding new syntaxes / language definitions" section][newsyn] of the
project's README for more details, but basically:

```bash
mkdir -p "$(bat --config-dir)/syntaxes"
cd "$(bat --config-dir)/syntaxes"
git clone https://github.com/ernstki/LDIF-Syntax.git
bat cache --build
bat --list-languages | grep -i ldif
```

### Converting syntax formats

The `.tmLanguage` file was converted into the [`.sublime-syntax` format][synref]
that appears in this fork using `sublime_syntax_convertor` from
[aziz/SublimeSyntaxConvertor][ssc], like so:

```
gem install --user sublime_syntax_convertor
cd "$(bat --config-dir)/syntaxes"
cd LDIF-Syntax
sublime_syntax_convertor .
```

Apart from that, no other changes were made to the `.sublime-syntax` file, nor
was any attempt made to verify the fidelity of the conversion within Sublime
Text.

I just wanted basic syntax highlighting for LDIF with `bat`, and am not a
Sublime Text user.


## References

* <https://forum.sublimetext.com/t/trying-to-convert-tmlanguage-syntax-to-sublime-syntax/53427>
* <https://forum.sublimetext.com/t/tmlanguage-to-sublime-syntax-convertor/17370>
  * _this thread is where I found the eventual solution, using
    `sublime_syntax_convertor`_


[ldif]: https://en.wikipedia.org/wiki/LDAP_Data_Interchange_Format
[rfc]: https://tools.ietf.org/html/rfc2849
[st3]: https://www.sublimetext.com/
[bat]: https://github.com/sharkdp/bat
[newsyn]: https://github.com/sharkdp/bat#adding-new-syntaxes--language-definitions
[synref]: https://www.sublimetext.com/docs/3/syntax.html
[ssc]: https://github.com/aziz/SublimeSyntaxConvertor
