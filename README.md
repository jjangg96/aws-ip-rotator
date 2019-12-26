AWS IP Rotator
==============

Changes a EC2 machine's IP address every ten minutes using Elastic IP.

Requirement
```
sudo apt-get -y install awscli
sudo apt-get -y install jq
```

Requires IAM role
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "ec2:ReleaseAddress",
                "ec2:DescribeAddresses",
                "ec2:AssociateAddress",
                "ec2:AllocateAddress"
            ],
            "Resource": "*"
        }
    ]
}
```

Usage
-----

Change your IP (one off):


```bash
./aws-ip-rotator.sh
```

Start rotating IPs every ten minutes:

```bash
./aws-ip-rotator.sh start
```

Stop it:

```bash
./aws-ip-rotator.sh stop
```
