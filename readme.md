# riot-archive

A lightweight library for reading RAF files which are used in League of Legends. Licensed under the GPLv3.

## Example usage

#### Get a file stream for a file contained in a single archive
```csharp
var archive = RiotArchive.FromFile("archive.raf");
var stream = archive["file1.txt"].GetStream();
```
#### Get a file stream for a file from a collection of archives
Sometimes content may be split into multiple archives. The `RiotArchiveCollection` offers easy access to any file within the entire RAF collection.
```csharp
var archives = new RiotArchiveCollection(Directory.GetFiles("C:/raf-archives/", "*.raf"));
archives.Open();
var stream = archives["cool-kids.pdf"].GetStream();
```
#### Get a list of files whose file paths match a regular expression
```csharp
var matchedFiles = archives.GetFiles(@"^awesome.*\.txt$");
```
The `RiotArchive` and `RiotArchiveCollection` classes share a common API so they are interchangeable.

## Dependencies
No dependencies - all the code needed is embedded within the assembly.
