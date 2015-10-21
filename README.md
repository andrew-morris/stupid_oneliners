# Stupid One-Liners

## Miscellaneous 

Use Amazon AWS CLI to get all IP addresses from all regions

```
$ for i in $(aws ec2 describe-regions | grep RegionName | cut -d'"' -f4);do aws ec2 describe-instances --region $i | grep PublicIpAddress | cut -d'"' -f4; done
```

Delete all GIF and HTML files in your current directory and any subdirectories

```
$ for i in $(file * | grep "GIF\|HTML" | cut -d':' -f1); do rm $i;done
```

Rename all files in current directory and subdirectory to their MD5 hashes (OS X)

```
$ for i in $(find . -type f);do mv $i $(md5 $i | cut -d' ' -f4);done
```
