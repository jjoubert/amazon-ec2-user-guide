# Enable or Disable Detailed Monitoring for Your Instances<a name="using-cloudwatch-new"></a>

By default, your instance is enabled for basic monitoring\. You can optionally enable detailed monitoring\. After you enable detailed monitoring, the Amazon EC2 console displays monitoring graphs with a 1\-minute period for the instance\. The following table describes basic and detailed monitoring for instances\.


| Monitoring Type | Description | 
| --- | --- | 
|  Basic  |  Data is available automatically in 5\-minute periods at no charge\.  | 
|  Detailed  |  Data is available in 1\-minute periods for an additional cost\. To get this level of data, you must specifically enable it for the instance\. For the instances where you've enabled detailed monitoring, you can also get aggregated data across groups of similar instances\. For information about pricing, see the [Amazon CloudWatch product page](https://aws.amazon.com/cloudwatch)\.  | 

## Enabling Detailed Monitoring<a name="enable-detailed-monitoring"></a>

You can enable detailed monitoring on an instance as you launch it or after the instance is running or stopped\. Enabling detailed monitoring on an instance does not affect the monitoring of the EBS volumes attached to the instance\. For more information, see [Amazon CloudWatch Metrics for Amazon EBS](using_cloudwatch_ebs.md)\.

**To enable detailed monitoring for an existing instance \(console\)**

1. Open the Amazon EC2 console at [https://console\.aws\.amazon\.com/ec2/](https://console.aws.amazon.com/ec2/)\.

1. In the navigation pane, choose **Instances**\.

1. Select the instance and choose **Actions**, **CloudWatch Monitoring**, **Enable Detailed Monitoring**\.

1. In the **Enable Detailed Monitoring** dialog box, choose **Yes, Enable**\.

1. Choose **Close**\.

**To enable detailed monitoring when launching an instance \(console\)**  
When launching an instance using the AWS Management Console, select the **Monitoring** check box on the **Configure Instance Details** page\.

**To enable detailed monitoring for an existing instance \(AWS CLI\)**  
Use the following [monitor\-instances](https://docs.aws.amazon.com/cli/latest/reference/ec2/monitor-instances.html) command to enable detailed monitoring for the specified instances\.

```
aws ec2 monitor-instances --instance-ids i-1234567890abcdef0
```

**To enable detailed monitoring when launching an instance \(AWS CLI\)**  
Use the [run\-instances](https://docs.aws.amazon.com/cli/latest/reference/ec2/run-instances.html) command with the `--monitoring` flag to enable detailed monitoring\.

```
aws ec2 run-instances --image-id ami-09092360 --monitoring Enabled=true...
```

## Disabling Detailed Monitoring<a name="disable-detailed-monitoring"></a>

You can disable detailed monitoring on an instance as you launch it or after the instance is running or stopped\.

**To disable detailed monitoring \(console\)**

1. Open the Amazon EC2 console at [https://console\.aws\.amazon\.com/ec2/](https://console.aws.amazon.com/ec2/)\.

1. In the navigation pane, choose **Instances**\.

1. Select the instance and choose **Actions**, **CloudWatch Monitoring**, **Disable Detailed Monitoring**\.

1. In the **Disable Detailed Monitoring** dialog box, choose **Yes, Disable**\.

1. Choose **Close**\.

**To disable detailed monitoring \(AWS CLI\)**  
Use the following [unmonitor\-instances](https://docs.aws.amazon.com/cli/latest/reference/ec2/unmonitor-instances.html) command to disable detailed monitoring for the specified instances\.

```
aws ec2 unmonitor-instances --instance-ids i-1234567890abcdef0
```