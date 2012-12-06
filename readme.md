# riot-archive

A lightweight library for reading Riot Archive Files which are used in League of Legends. Licensed under the GPLv3.

## Example usage

#### Opening a single archive file

    var archive = RiotArchive.FromFile("...");
    var fileStream = archive["path/to/file.txt"].GetStream();
    // do something with the file stream

#### Opening a collection of archive files as a single archive

	var archives = new RiotArchiveCollection(Directory.GetFiles("...", "*.raf"));
	archives.Open();
    var fileStream = archives["path/to/file.txt"].GetStream();
    // do something with the file stream

#### Get a list of files that match a search criteria

    var matchedFiles = archives.GetFiles("^awesome.*\.txt$");

The `RiotArchive` and `RiotArchiveCollection` classes share a common structure, so they are interchangeable.

## Dependencies
No dependencies - all the code needed is embedded within the assembly.
