# The ACME dataset - Altered and Corrupted Midi Excerpts

TODO:
* Link to specific mdtk release which generated code
* Credit all sources of data

## Version 1.0 details

Count of degradations:
	* none: 2501
	* pitch_shift: 2501
	* time_shift: 2502
	* onset_shift: 2501
	* offset_shift: 2501
	* remove_note: 2502
	* add_note: 2501
	* split_note: 2502
	* join_notes: 2501

You will find the generated data within the zipped directory `acme` with subdirectories
	* `clean` - contains the extracted clean excerpts
	* `altered` - contains the excerpts altered by the degradations described in `metadata.csv`

`metadata.csv` describes:
	* (the id number for) the type of degradation used for the alteration
	* the path for the altered and clean files
	* which split (train, valid, test) the file should be used in
	* in which corpus and on what line the file is located

`degradation_ids.csv` is a mapping of degradation name to the id number used in `metadata.csv`

The `{train,valid,test}_cmd_corpus.csv` are command-based (note_on, note_off, shift) versions of the acme data more convenient for our provided pytorch Dataset classes avaialble in the [Midi Degradation ToolKit package](https://github.com/JamesOwers/midi_degradation_toolkit).

Similarly, `{train,valid,test}_pr_corpus.csv` are piano-roll-based versions of the acme data more convenient for our provided pytorch Dataset classes avaialble in the [Midi Degradation ToolKit package](https://github.com/JamesOwers/midi_degradation_toolkit).

### Reproducibility
To reproduce this dataset again, install the [Midi Degradation ToolKit package](https://github.com/JamesOwers/midi_degradation_toolkit) and run `./make_dataset --seed 1762218506`
