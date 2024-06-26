# DS XML

XML exports from https://catalog.digital-scriptorium.org

These files are split to avoid GitHub requiring [`git-lfs`](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage) for files over 50MB.

The files are gzipped and split using the `split` command:

```
$ gzip export.xml
# => export.xml.gz
# split files into 8MB chunks:
$ spit -b 8m export.xml.gz export.xml.gz_
# => export.xml.gz_aa, export.xml.gz_ab, export.xml.gz_ac, export.xml.gz_ad, ...
```


To reassemble and decompress the files use the `cat` command:

```
$ cat export.xml.gz_* | gunzip -c > export.xml
```