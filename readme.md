# riot-archive

A lightweight library for reading Riot Archive Files which are used in League of Legends. Licensed under the GPLv3.

## Example usage

#### Opening a single archive file
```csharp
var archive = RiotArchive.FromFile("archive.raf");
var stream = archive["file1.txt"].GetStream();
```
#### Opening a collection of archive files as a single archive
```csharp
var archives = new RiotArchiveCollection(Directory.GetFiles("documents/archives", "*.raf"));
archives.Open();
var stream = archives["cool-kids.pdf"].GetStream();
```
#### Get a list of files whose file path match a regular expression
```csharp
var matchedFiles = archives.GetFiles(@"^awesome.*\.txt$");
```
The `RiotArchive` and `RiotArchiveCollection` classes share a common structure, so they are interchangeable.

## Dependencies
No dependencies - all the code needed is embedded within the assembly.
