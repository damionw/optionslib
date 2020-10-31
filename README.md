# Command line option handling lib #

## Description ##

This library wraps getopt to provide higher order command line option
processing akin to python argparse, etc

## Basic Usage ##

    #!/usr/bin/env bash

    # Import OptionLib components
    . "$(optionslib --lib)"

    # Provide command description
    optionslib::parse::description "OptionLib Demo"

    # Define command line options
    optionslib::parse::config "
        long_options=--help short_options=-h action=show_help description='show help options'
        long_options=--start: action=store_var name=start_option description='start the service'
        long_options=--go: action=command name=start_service description='Do nothing'
    "

    # Process command line arguments
    optionslib::parse::parse_arguments "$@"
