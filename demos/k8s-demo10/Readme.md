# Jobs & CronJobs

## Jobs

Jobs are small Tasks that process data independently. Jobs actually use "Pod" to perform
the activities. Onces the POD execution is completed, it's status changes to 'COMPLETED' and it's stopped.

## CronJobs

Jobs which are Recurrent, can scheduled to run at particular intervals.
Schedule Syntax:
    [MINUTES] [HOURS] [DAY-OF-MONTH] [MONTH] [WEEK-DAY]
    */1       *       *              *       4-6
    15        9       *              *       *          Every Day at 9:15 AM
    1         *       *              *       *          Every Day at 1 Minute past Every Hour

Link: https://tecadmin.net/crontab-in-linux-with-20-examples-of-cron-schedule/

1. Create namespace:

    `kubectl create namespace mahendra`

2.  To get Pods from namespace

    `kubectl get pods -n mahendra`

