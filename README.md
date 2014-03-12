indexer
=======

Creates an index using the provided column as key, in which each entry
specifies the byte position in the file. Say we name the chosen column you
choose as <key>, by default an entry is created after passing <interval>
different <keys>. So between an entry and another there are <interval>
different <keys>. For example: If we want to index a file in which the column
are IPs, by default is indexed in a way that between an IP index entry and the
next there are <interval> different IPs in the original file. Using the option
-L we can change this behaviour. With the option -L the indexer creates an
entry for every 10 lines. With the option -T, we are assuming that the chosen
column is a timestamp (with ms) so the interval is a time in minutes and the
indexer creates an entry for each <interval>*60 seconds.

optional arguments:
  -h, --help            show this help message and exit
  -c COLUMN, --column COLUMN
                        Column to be indexed by, column of the <key>.
                        Numbering starting in 0. Zeroth column as default.
  -F, --no-first-line   Use it if you want to exclude de first line.
  -i INPUT, --input INPUT
                        Input file. Default: stdin.
  -I INTERVAL, --interval INTERVAL
                        With no -L and -T option the interval is how many
                        different <keys> we want between an entry and the
                        next. With the -L option it would be the line interval
                        whereby each entry is created. In case of using -T
                        option it would mean minutes.
  -L, --line            Use it if the interval is a number of lines. An entry
                        will be created for each interval of lines. Not
                        compatible with option -T.
  -s SEPARATOR, --separator SEPARATOR
                        Defines the input field separator. Space character as
                        default.
  -S, --sorted          Use it if the provided file is sorted. Unsorted input
                        supported just for -T index mode.
  -o OUTPUT, --output OUTPUT
                        Index output filename. Default: stdout.
  --no-progress-bar     Disable progress bar.
  -T, --time            Use it if the chosen column is a timestamp, thus the
                        interval would mean minutes.
  -V, --version         Returns the version of the app.
  --httpdissector       Default parameters for httpDissector input.
  --flowprocess         Default parameters for flowProcess input.
