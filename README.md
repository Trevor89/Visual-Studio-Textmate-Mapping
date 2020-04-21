# Visual-Studio-Textmate-Mapping
Visual Studio Syntax mapping to textmate conventions
```
Textmate Convention                  VS Font                 Description
------------------------------------------------------------------------
comment                             — Comment              - for comments.
comment.line                        — Comment              - line comments, we specialize further so that the type of comment start character(s) can be extracted from the scope. 
comment.line.double-slash           — Comment              - // comment
comment.line.double-dash            — Comment              - -- comment
comment.line.number-sign            — Comment              - # comment
comment.line.percentage             — Comment              - % comment
comment.line.character              — Comment              - other types of line comments.
comment.block                       — Comment              - multi-line comments like /* … */ and <!-- … -->. 
comment.block.documentation         — Comment              - embedded documentation.

constant                            — Default Text         - various forms of constants.
constant.numeric                    — Number               - those which represent numbers, e.g. 42, 1.3f, 0x4AB1U.
constant.character                  — Default Text         - those which represent characters, e.g. &lt;, \e, \031. 
constant.escape                     — Default Text         - escape sequences like \e would be constant.character.escape.
constant.language                   — keyword              - constants (generally) provided by the language which are “special” like true, false, nil, YES, NO, etc.
constant.other                      — Default Text         - other constants, e.g. colors in CSS.

entity                              — Default Text         - an entity refers to a larger part of the document, for example a chapter, class, function, or tag. We do not scope the entire entity as entity.* (we use meta.* for that). But we do use entity.* for the “placeholders” in the larger entity, e.g. if the entity is a chapter, we would use entity.name.section for the chapter title.
entity.name                         — Type                 - we are naming the larger entity. 
entity.name.function                — Type                 - the name of a function.
entity.name.type                    — Type                 - the name of a type declaration or class.
entity.name.tag                     — Markup node          - a tag name.
entity.name.section                 — Type                 - the name is the name of a section/heading.
entity.other                        — Default Text         - other entities. 
entity.other.inherited-class        — Type                 - the superclass/baseclass name.
entity.other.attribute-name         — Markup attribute     - the name of an attribute (mainly in tags).

invalid                             — Default Text         - stuff which is “invalid”.
invalid.illegal                     — Default Text         - illegal, e.g. an ampersand or lower-than character in HTML (which is not part of an entity/tag).
invalid.deprecated                  — Default Text         - for deprecated stuff e.g. using an API function which is deprecated or using styling with strict HTML.

keyword                             — keyword              - keywords (when these do not fall into the other groups).
keyword.control                     — keyword              - mainly related to flow control like continue, while, return, etc.
keyword.operator                    — Default Text         - operators can either be textual (e.g. or) or be characters.
keyword.operator.arithmetic         — Default Text         - operators can either be textual (e.g. or) or be characters.
keyword.other                       — Default Text         - other keywords.

markup                              — Default Text         - this is for markup languages and generally applies to larger subsets of the text.
markup.underline                    — Default Text         - underlined text. 
markup.underline.link               — Default Text         - this is for links, as a convenience this is derived from markup.underline so that if there is no theme rule which specifically targets markup.underline.link then it will inherit the underline style.
markup.bold                         — Default Text         - bold text (text which is strong and similar should preferably be derived from this name).
markup.heading                      — String               - a section header. Optionally provide the heading level as the next element, for example markup.heading.2.html for <h2>…</h2> in HTML.
markup.italic                       — Default Text         - italic text (text which is emphasized and similar should preferably be derived from this name).
markup.list                         — Default Text         - list items. 
markup.list.numbered                — Default Text         - numbered list items.
markup.list.unnumbered              — Default Text         - unnumbered list items.
markup.quote                        — Default Text         - quoted (sometimes block quoted) text.
markup.raw                          — Default Text         - text which is verbatim, e.g. code listings. Normally spell checking is disabled for markup.raw.
markup.other                        — Default Text         - other markup constructs.

meta                                — Default Text         - the meta scope is generally used to markup larger parts of the document. For example the entire line which declares a function would be meta.function and the subsets would be storage.type, entity.name.function, variable.parameter etc. and only the latter would be styled. Sometimes the meta part of the scope will be used only to limit the more general element that is styled, most of the time meta scopes are however used in scope selectors for activation of bundle items. For example in Objective-C there is a meta scope for the interface declaration of a class and the implementation, allowing the same tab-triggers to expand differently, depending on context.

storage                             — Default Text         - things relating to “storage”.
storage.type                        — keyword              - the type of something, class, function, int, var, etc.
storage.modifier                    — keyword              - a storage modifier like static, final, abstract, etc.

string                              — String               - strings.
string.quoted                       — String               - quoted strings. 
string.quoted.single                — Default Text         - single quoted strings: 'foo'.
string.quoted.double                — Default Text         - double quoted strings: "foo".
string.quoted.triple                — Default Text         - triple quoted strings: """Python""".
string.quoted.other                 — Default Text         - other types of quoting: $'shell', %s{...}.
string.unquoted                     — String               - for things like here-docs and here-strings.
string.interpolated                 — String               - strings which are “evaluated”: `date`, $(pwd).
string.regexp                       — String               - regular expressions: /(\w+)/.
string.other                        — String               - other types of strings (should rarely be used).

support                             — Default Text         - things provided by a framework or library should be below support.
support.function                    — keyword              - functions provided by the framework/library. For example NSLog in Objective-C is support.function.
support.class                       — Type                 - when the framework/library provides classes.
support.type                        — Type                 - types provided by the framework/library, this is probably only used for languages derived from C, which has typedef (and struct). Most other languages would introduce new types as classes.
support.constant                    — Default Text         - constants (magic values) provided by the framework/library.
support.variable                    — Default Text         - variables provided by the framework/library. For example NSApp in AppKit.
support.other                       — Default Text         - the above should be exhaustive, but for everything else use support.other.

variable                            — Default Text         - variables. Not all languages allow easy identification (and thus markup) of these.
variable.parameter                  — Default Text         - when the variable is declared as the parameter.
variable.language                   — keyword              - reserved language variables like this, super, self, etc.
variable.other                      — Default Text         - other variables, like $some_variables.
```
