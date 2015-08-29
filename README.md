# Stupid One-Liners

Use Amazon AWS CLI to get all IP addresses from all regions

```
# for i in $(aws ec2 describe-regions | grep RegionName | cut -d'"' -f4);do aws ec2 describe-instances --region $i | grep PublicIpAddress | cut -d'"' -f4; done
```
