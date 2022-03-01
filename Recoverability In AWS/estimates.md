## Minimum RTO for a single AZ outage

In this case RTO is the time to complete the switch to a different AZ. Minimum 60-120 seconds.

Documentation: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html

## Minimum RTO for a single region outage
An ERP application is deployed across multiple AZs in a single region. In the event of failure, 
the Recovery Time Objective (RTO) must be less than 3 hours, and the Recovery Point Objective (RPO) 
must be 15 minutes. The customer realizes that data corruption occurred roughly 1.5 hours ago.

## Minimum RPO for a single AZ outage

The RPO is typically 5 minutes, but you can find it by calling RDS:describe-db-instances:LatestRestorableTime. This time can vary from 10 minutes to hours, depending on the number of logs that need to be applied.

## Minimum RPO for a single region outage

Read replicas aim to be kept up to date with the primary DB so the read replica should have almost the same RPO as the primary DB. For some critical cases we can consider at most the RPO should be ±10 mins.