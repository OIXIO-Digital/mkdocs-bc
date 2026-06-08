## Failed Queue Notifier

Notification of job queue entries in error and too long in progress via email and restarting the entry.

### User permissions

A user with limited rights (not SUPER) must be assigned the user permission set CPC-JQ FAILQNOTIFIER.

### Setup

Search for Notification Groups and create a notification group to send notifications for job queue entries that have gone into error:

![3]

Assign users to the created notification group using the Notification Group Users button on the Notification Groups page:

![4]

Fill in the fields in the Notification Group Users table:![5]

- Notification Group Code -- the code of the created notification group

- User name -- the user to whom notifications will be sent

- Contact Email -- the email address to which the notification will be sent

- Authentication Email -- the email address used to log into BC

Search for Ext. Job Queue Setup, where you specify the notification group code and the maximum job queue time, how long (hours) a job queue entry can be in the In Progress status before a notification is sent about the job queue entry being in progress for too long.

![3][1]To send notifications and restart entries in error, a job queue entry must be created.

Search for Job Queue Entries and create a new one. From the Triggering Object Type field, select Codeunit, Triggering Object ID 24015620. From the Recurrence block, specify the days on which the job queue entry status check will take place and the number of minutes between executions specify how often the statuses are checked (in minutes).

![][2]

  [3]: ./media/en/image1.png
  [4]: ./media/en/image2.png
  [5]: ./media/en/image3.png
  [1]: ./media/en/image4.png
  [2]: ./media/en/image5.png

