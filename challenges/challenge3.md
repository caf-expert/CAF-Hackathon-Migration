# CAF Hackathon

Adopt: **Migrate**

![CAF Hackathon Header](/media/caf-hackathon-header.png)

In this challenge we will build the LandingZone for the migration.

## Challenge 3

The Director of IT wants to validate that the migration strategy is sound, and the migrated applications will not only be operational but also secure and compliant. Building this trust with the business is a key component of the migration to Azure. By validating not only your architecture but also your approach, you can make sure that the business is a partner in the move to the cloud. This will require testing in isolation so that the existing on-premises environment is not impacted. This will allow the relevant teams at Contoso to perform automated testing, offers application owners the opportunity to provide meaningful feedback, and allows for the migration to be performed as many times as it is needed to get it right. In addition to maintaining their current segmentation, IT leadership would also like to introduce infrastructure to better position their applications for growth in the future. Moving to Azure will allow IaaS hosted applications to be more resilient by adopting features of the Azure platform that are only available in the cloud. To position themselves for better resiliency for both the Contoso and Contoso Admin web applications, the Network Operations team would like to incorporate a load balancer into their architecture to allow for greater flexibility and elasticity in the front-end layer of their applications.

[Target Architecture](./../media/application_architecture_target.png)

## Customer Requirements

Contoso has the following requirements which you should take into consideration:

- The migrated applications must maintain their segmentation at the network layer. For example, the customer-accessible web front-end for the Contoso Mortgage application can only communicate with the application server, and the application server can only communicate with the database server.
- The servers must be fully operational, including having the ability to access the servers using domain credentials without connectivity to any on-premises domain controllers.
- Due to security requirements, server administrators will not be able to use Remote Desktop over the public internet and no public IPs can be associated with Azure-hosted servers.
- Members of the CM Server Admins security group should be granted rights to use any RDP or remote connectivity solution.
- While administrators can connect across the previously established site-to-site connection, a solution must be implemented which does not rely on the presence of the site-to-site connection. Administrators must be able to connect if the connection is down or they are not working from their on-premises site.
- Each application must have a dedicated testing URL that can be distributed to testers.
- A load-balancing technology should be implemented for any user-facing servers (web front ends).

## Success Criteria

- Network segmentation is in place and limits lateral movement between application layers, including non-application communication such as RDP access.
- The URL you select for testing and validating each application needs to be resolvable from the public internet.
- Server administrators in the CM Server Admins security group can access all of the migrated servers in a secure manner which does not require opening RDP access to the public internet for any migrated servers.
- If cmad1 is turned off or hybrid network connectivity between on-premises and Azure is lost, the applications in the isolated testing environment can still function.
- A load-balancing technology has been introduced in front of any user-facing web servers and the target applications remain functional.
- For any migrated servers, native Azure functionality such as the Run Command should be available as if the server was provisioned from the Azure Marketplace.

Let's build up everything in Azure so that the VMs could be migrated to your LandingZone (Use Resource Group LandingZone for this). And describe how you will address the success criteria.
