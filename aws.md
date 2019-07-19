AWS:-
---

1.amazon web services (cloud computing)
2.azure,gcp(google cloude platform)
3.

networking&contentDelivery:-
---

vpc:- virtual private cloud. To provide complete control with you and access to all.
direct connect:- Dedicated network.
route53:- DNS google.com -> take dns -> convert into numerics. why route53?
port name of dns is 53 so they called route53.
cloud Front:- edge location is the place that caches the data.Example your data is stored somewhere in us location if someone from india wants to use your data,the data can be cached in mumbai so that
no need to pull data from US location.

compute:-
---

EC2:-
---
it's a virtualization server.


storage:-
---
S3:-
---
simple storage service. scalable storage in the cloud. secure 
highly scalable.pay for what you use.Object based storage.

s3 permissions:-
---

1. In the permissions tab click on public Access settings
2. click on edit
3. deselect the Block new public bucket policies option 
4. save your changes
5. go back to bucket policy and try again.

Elastic File System:-
---
It is same as like NAS.
It use to store the number of EC2 instance into a single elastic file system.
It is block level storage.

Glacier:-
---
use this to take backup and arachive file.
data access takes 2-4 hours	retrieval time.
used as for backup.
secure and low cost storage option.
long time backup.

Storage Gateway:-(Hybrid storage integration)
---
The AWS storage Gateway is a service connecting an our own data center to aws for transfer data securly.

Database services:-
----------

RDS:-
---
Relational Database service consisting of many DB's(oracle,posgresql,MySQL and so on)in the cloud. Managed Relational DB services.

DynamoDB:-
---
Managed NosqlDB in AWS.Non RDS.

ElastiCache:-
---
In-memory cached to help the DB.Cache the data in Colud to improve DB performance and to reduce DB load.

RedShift:-
---
Fast,simple,cost effective data warehousing solution from AWS.
use this to create DB image and place into RedShift then it's work as like a RedShift.
