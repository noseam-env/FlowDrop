# TFA Archive

TFA (Transfer Files Archive) simplified version of the old cpio format

This archive was created to simplify the virtualization of the archive in order to avoid the creation of temporary files

Virtualization allows you to read the archive directly from the disk without writing it first

There are no blocks, as in tar, here

## Specification

### Header

Size: `60 bytes`

| Field    | Size | Absolute Pos | Description                                      |
|----------|------|--------------|--------------------------------------------------|
| magic    | 4    | 0-3          | magic field, value `tfa\0`                       |
| version  | 1    | 3-4          | tfa version, currently `\0`                          |
| typeflag | 1    | 4-5          | currently unused                                 |
| unused   | 4    | 5-9          | reserved bytes                                   |
| mode     | 8    | 9-17         | file permissions in bitset<9>                    |
| ctime    | 12   | 17-29        | file creation time                               |
| mtime    | 12   | 29-41        | file last modification time                      |
| namesize | 6    | 41-47        | size of file name in bytes (including last `\0`) |
| filesize | 12   | 47-59        | total file size in bytes                         |

### Structure

| Header   | File Name       | File Data       | Header   | File Name         |     |
|----------|-----------------|-----------------|----------|-------------------|-----|
| 60 bytes | header.namesize | header.filesize | 60 bytes | bytes from header | ... |
