# How does Snyk count assets

## Billable assets

Managed Billable Assets are the resources, assets, and configuration files accessed through or managed by the customer in Snyk AppRisk.

According to Snyk, the following are considered Managed Billable Assets against the Customer's Subscription Allocation:

| Asset type                                                                                                                                                                                                                                                                            | Billable asset examples                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| <p><strong>Repository Assets:</strong></p><p>Source Code Repository, where Snyk counts the total repositories.</p><p><br></p>                                                                                                                                                         | github.com/snyk/hello-world              |
| <p><strong>Container Image Assets</strong></p><p>Represent the built image that is found in a customer’s estate, where images are counted based on the globally unique identifiers, like image IDs and SHA, that may contain an application and all of its software dependencies.</p> | dockerhub.com/my-company/my-image:latest |

## Asset Usage Policy

Snyk may monitor customer billable asset volumes on a daily basis and actively review customer utilization on a rolling thirty (30) day period. If a customer’s billable asset usage exceeds the limit granted by the plan purchased by twenty percent (20%) on a rolling ninety (90) day period or by one-hundred percent (100%) for a period of thirty (30) days, Snyk may notify the customer to discuss the overage and, \[if action is required], provide an expansion invoice to increase the billable asset allocation. Except in unusual circumstances, Snyk will not invoice retroactively for Managed Billable Asset overages.\\
