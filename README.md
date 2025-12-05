Onkyo eISCP Control, .NET version
[![CI Workflow](https://github.com/mitchcapper/onkyo-eiscp-dotnet/actions/workflows/dotnet-build.yml/badge.svg)](https://github.com/mitchcapper/onkyo-eiscp-dotnet/actions/workflows/dotnet-build.yml)

This was originally a direct port of the Python [Python version](https://github.com/mitchcapper/onkyo-eiscp),
and you should have a look at the documentation there to get started.  It has had some additional enhancements for stronger typing and parameter validation/conversion.  It includes both a .NET library and a console application for use.


## You Can Help!
Newer versions of this library are only possible by getting update ISCP_AVR_*.xlsx files with the new protocols.  These files are normally only given to dealers/installers so if you have a newer version please email it to me (my email is on [my github page](https://github.com/mitchcapper) although you may need to sign in to see it) so we can support newer functions.

 Brand new receivers will generally work with this library out of the box, but the model filtering will not work as it won't know about the new version.  If you want the model filter functions to work, I recommend finding the prior model number and either editing the library adding the new one to its groups, or tell this library that your model is the last model.


 ## Usage / Binary Versions

You can use either the latest CI build or a release from the release section if you don't want to build from source.  You can use the CLI version with just:

`onkyo system-power:on`

is all you need.  It will try to autodiscover local receivers on your network.

## Onkyo Command Line (CLI)
```

Usage:
  onkyo [--host <host>] [--port <port>] [--all] [--name <name>] <command>...
  onkyo --discover
  onkyo --help-commands [<zone> <command>]
  onkyo -h | --help

Selecting the receiver:

  --host, -t <host>     Connect to this host
  --port, -p <port>     Connect to this port [default: 60128]
  --all, -a             Discover receivers, send to all found
  --name, -n <name>     Discover receivers, send to those matching name.

If none of these options is given, the program searches for receivers,
and uses the first one found.

  --discover            List all discoverable receivers, can limit to a specific host with --host
  --help-commands       List available commands.

Special commands (these are not official by implemented by the CLI):
  dump_xml - Dump the full XML configuration of the receiver (NRI command)
  list_inputs to see available input sources

Examples:
  onkyo power:on source:pc volume:75
    Turn receiver on, select ""PC"" source, set volume to 75.
  onkyo zone2.power:standby
    To execute a command for zone that isn't the main one.
```


## Generating this Library
While you can normally use the source directly if doing this yourself you need the `eiscp-commands.yaml` file from the python repo above.  The Generate project here converts that into the .CS classes that the onkyo-eiscp project is then used to compile those .net classes into the library dll. onyko executable is the command line tool.
