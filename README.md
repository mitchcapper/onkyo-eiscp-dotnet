Onkyo eISCP Control, .NET version
---------------------------------

This was originally a direct port of the Python [Python version](https://github.com/mitchcapper/onkyo-eiscp),
and you should have a look at the documentation there to get started.  It has had some additional enhancements for stronger typing and parameter validation/conversion. 

However, note that under "releases" you'll find a compiled binary of the command line tool that
you can use to get started straight away:

    onkyo system-power:on
    
is all you need.



## Generating this Library
While you can normally use the source directly if doing this yourself you need the `eiscp-commands.yaml` file from the python repo above.  The Generate project here converts that into the .CS classes that the onkyo-eiscp project is then used to compile those .net classes into the library dll. onyko executable is the command line tool.