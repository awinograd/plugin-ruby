# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Changed
- [INTERNAL] Provide the `makeList` utility for the nodes that are lists from within ripper.

## [0.4.0] - 2019-02-12
### Added
- Support the `trailingComma` configuration option (defaults to `false`). (Thanks to @Overload119 for the request.)

### Changed
- Pass the code to be formatted over `stdin`. (Thanks to @NoahTheDuke for the report.)

## [0.3.7] - 2019-02-11
### Changed
- Split up statements even if they started on the same line with `;`s unless they are within an embedded expression.
- Properly handle escaped quotes within strings.

## [0.3.6] - 2019-02-10
### Changed
- Support the `not` operator properly. (Thanks to @AlanFoster for the report.)
- Handle comments properly inside `if`, `unless`, and `when` nodes. (Thanks to @AlanFoster for the report.)

## [0.3.5] - 2019-02-09
### Changed
- Handle lonely operators in Ruby `2.5`.

## [0.3.4] - 2019-02-09
### Changed
- Comments are now properly attached inside `defs` nodes.
- Support multiple inline comments on nodes.
- Support inline comments from within the `EXPR_END|EXPR_LABEL` lexer state.
- Stop transforming multistatement blocks with `to_proc`. (Thanks to @cbothner.)
- `do` blocks necessarily need to break their parent nodes.
- Handle `next` node edge case with `args_add` as the body. (Thanks to @eins78 for the report.)

## [0.3.3] - 2019-02-09
### Changed
- Command nodes within conditionals now break parents to disallow them from being turned into ternary expressions. (Thanks to @bugthing for the report.)
- Properly escape double quotes when using `preferSingleQuotes: false`. (Thanks to @awinograd for the report.)

## [0.3.2] - 2019-02-09
### Changed
- [INTERNAL] Don't define duplicated methods in the parser.
- Let prettier know about `.rb` and `.rake` files so you don't have to specify the parser when running.
- Renamed the package to @prettier/plugin-ruby.

## [0.3.1] - 2019-02-07
### Changed
- Automatically add parens to method declarations.
- Handle comments on bare hash assocs.
- Handle `method_add_block` nodes where the statements may be nested one more level.
- Handle heredocs nested no matter how many levels deep.

## [0.3.0] - 2019-02-07
### Added
- Support squiggly heredocs.
- Support straight heredocs.

### Changed
- Ignore current indentation when creating embdocs so that `=begin` is always at the beginning of the line.
- [INTERNAL] Move `regexp_add` and `regexp_new` handling into the parser.
- [INTERNAL] Move `xstring_add` and `xstring_new` handling into the parser.
- [INTERNAL] Move `string_add` and `string_content` handling into the parser.
- [INTERNAL] Move `mrhs_add` and `mrhs_new` handling into the parser.
- [INTERNAL] Move `mlhs_add` and `mlhs_new` handling into the parser.

## [0.2.1] - 2019-02-06
### Changed
- Handle brace blocks on commands properly.
- Break parent and return `do` blocks when called from a `command` node.
- Handle edge cases with `if` statements where there is no body of the if (so it can't be converted to a ternary).

## [0.2.0] - 2019-02-06
### Added
- Handle `methref` nodes from Ruby `2.7`.
- Allow `module` nodes to shorten using `;` when the block is empty.

### Changed
- Handle splat within an array, as in `[1, 2, *foo]`.
- Disallow comments from being attached to intermediary regex nodes.
- Fix `to_proc` transforms to reference the method called as opposed to the parameter name.
- [INTERNAL] Change statement lists to be generated within the parser instead of the printer, thereby allowing finer control over comments.
- [INTERNAL] Completely revamp comment parsing by switching off the internal lexer state from `ripper`. This should drastically increase accuracy of comment parsing in general, and set us up for success in the future.
- Allow comments to be attached to `CHAR` nodes.
- [INTERNAL] Disallow comments from being attached to `args_new` nodes.
- [INTERNAL] Track start and end lines so we can better insert block comments.
- [INTERNAL] Handle intermediary array nodes in the parse for better comment handling.

## [0.1.2] - 2019-02-05
### Changed
- Handle guard clauses that return with no parens.

## [0.1.1] - 2019-02-05
### Changed
- Handle class method calls with the `::` operator.
- Handle strings with apostrophes when using `preferSingleQuote`.
- [INTERAL] Have travis run multiple ruby versions.
- Explicitly fail if ruby version is < `2.5`.
- Disallow comments from being attached to intermediary string nodes.

## [0.1.0] - 2019-02-04
### Added
- Initial release 🎉

[Unreleased]: https://github.com/CultureHQ/add-to-calendar/compare/v0.4.0...HEAD
[0.4.0]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.7...v0.4.0
[0.3.7]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.6...v0.3.7
[0.3.6]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.5...v0.3.6
[0.3.5]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.4...v0.3.5
[0.3.4]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.3...v0.3.4
[0.3.3]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.2...v0.3.3
[0.3.2]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.1...v0.3.2
[0.3.1]: https://github.com/CultureHQ/add-to-calendar/compare/v0.3.0...v0.3.1
[0.3.0]: https://github.com/CultureHQ/add-to-calendar/compare/v0.2.1...v0.3.0
[0.2.1]: https://github.com/CultureHQ/add-to-calendar/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/CultureHQ/add-to-calendar/compare/v0.1.2...v0.2.0
[0.1.2]: https://github.com/CultureHQ/add-to-calendar/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/CultureHQ/add-to-calendar/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/CultureHQ/add-to-calendar/compare/61f675...v0.1.0
