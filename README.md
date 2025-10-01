# climax

[![Build status](https://github.com/miguelgrinberg/climax/workflows/build/badge.svg)](https://github.com/miguelgrinberg/climax/actions) [![codecov](https://codecov.io/gh/miguelgrinberg/climax/branch/main/graph/badge.svg)](https://codecov.io/gh/miguelgrinberg/climax)

A lightweight argparse wrapper inspired by click.

Climax is a little argparse wrapper, with a decorator based syntax heavily
inspired by Armin Ronacher's [click](http://click.pocoo.org/). Climax can
import native argparse parsers as sub-commands, and can also export itself as
a native parser, providing full interoperability with existing argparse
based solutions.

## JSON Output

Climax supports outputting command structure information in JSON format instead of
standard help text. This is useful for programmatic introspection, generating
documentation, or building shell completion systems.

To enable JSON output, set the `CLIMAX_JSON` environment variable to `true`:

```bash
# Standard help output
$ python my_script.py --help
usage: my_script.py [-h] [--verbose] {deploy,config} ...
...

# JSON output
$ CLIMAX_JSON=true python my_script.py --help
{
  "prog": "my_script.py",
  "description": "My CLI application",
  "arguments": [...],
  "subcommands": {...}
}
```

The JSON output includes complete information about:
- Command arguments and options
- All subcommands (recursively)
- Help text, types, defaults, and constraints
- Usage patterns

Supported values for `CLIMAX_JSON`: `true`, `1`, `yes`, `on` (case-insensitive).

## Resources

- [Documentation](http://climax.readthedocs.io/en/latest/)
- [PyPI](https://pypi.python.org/pypi/climax)
- [Change Log](https://github.com/miguelgrinberg/climax/blob/main/CHANGES.md)
