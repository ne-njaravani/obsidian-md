- Infrastructure, like data centers and networking connectivity, still exists as the foundation of every cloud application. 
- In AWS, this physical infrastructure makes up the AWS Global Infrastructure, in the form of Regions and Availability Zones.

# Regions
- geographic locations worldwide where AWS hosts its data centers
- named after the location where they reside
	- e.g. in USA Region in Northern Virginia is called the Northern Virginia Region
- Each AWS Region is associated with a geographical name and a Region code.
	- e.g. - **us-east-1** is the first Region created in the eastern US area. The geographical name for this Region is N. Virginia.

## Choosing the right region
- AWS Regions are independent from one another
- Without explicit customer consent and authorization, data is not replicated from one Region to another
- Four aspects to consider when deciding which AWS Region to host apps and workloads:
	- Latency
		- the delay between a request for data and the response
		- If your app is sensitive to latency
			- choose a Region that is close to your user base
				- helps prevent long wait times for your customers.
		- Synchronous applications such as gaming, telephony, WebSockets, and Internet of Things (IoT) are significantly affected by high latency
		- Asynchronous workloads, such as ecommerce applications, can also suffer from user connectivity delays
	- Price
		- vary from one Region to another
			- Due to the local economy and the physical nature of operating data centers
			- Internet connectivity, imported equipment costs, customs, real estate, and other factors impact region's pricing
		- Instead of charging a flat rate worldwide
			- AWS charges based on the financial factors specific to each Region
	- Availability
		- Some services might not be available in some Regions
			- AWS doc provides table showing services available in each region
	- Compliance
		- Enterprise companies often must comply with regulations that require customer data to be stored in a specific geographic territory.
		- choose a Region that meets your compliance requirements.

# Availability Zones
- Inside every Region is a cluster of Availability Zones (AZs)
- An AZ consists of one or more data centers with redundant power, networking, and connectivity
- These data centers operate in discrete facilities in undisclosed locations
- They are connected using redundant high-speed and low-latency links
- Also have code names
	- Because they are located inside Regions, they can be addressed by appending a letter to the end of the Region code name
		- e.g. - **us-east-1a** is an Availability Zone in us-east-1 (N. Virginia Region).
		- Therefore, if you see that a resource exists in us-east-1c, you can infer that the resource is located in Availability Zone c of the us-east-1 Region.
	- ![[Pasted image 20251106144340.png]]

# Scope of AWS services
- Depending on the service that you use, your resources are either deployed at the AZ, Region, or Global level
- Each service is different
	- you MUST understand how the scope of a service might affect your application architecture
- When you operate a Region-scoped service, 
	- you only need to select Region you want to use
- If you are not asked to specify an individual Availability Zone to deploy the service in, 
	- this is an indicator that the service operates on a Region-scope level. For region scoped services:
		- AWS automatically performs actions to increase data durability and availability
- some services ask you to specify an Availability Zone. 
	- With these you are often responsible for increasing the data durability and high availability of these resources.

# Maintaining resiliency
- To keep your app available, you must maintain high availability and resiliency
- best practice for cloud architecture is to use Region-scoped, managed services
	- These services come with availability and resiliency built in
		- When that is not possible, make sure your workload is replicated across multiple AZs
- at a minimum, you should use two AZs
	- That way, if an Availability Zone fails, your application will have infrastructure up and running in a second Availability Zone to take over the traffic.
- ![[Pasted image 20251106151716.png]]


# Edge locations
- global locations where content is cached
	- e.g. if your media content is in London and you want to share video files with your customers in Sydney, you could have the videos cached in an edge location closest to Sydney
		- would make it possible for your customers to access the cached videos more quickly than accessing them from London. 
	- Currently, there are over 400+ edge locations globally.
- Amazon CloudFront delivers your content through a worldwide network of edge locations
	- When a user requests content that is being served with CloudFront
		- request is routed to the location that provides the lowest latency
		- So that content is delivered with the best possible performance
	- CloudFront speeds up the distribution of your content by routing each user request through the AWS backbone network to the edge location that can best serve your content.
- ![[Pasted image 20251106152511.png]]

# Resources 

For more information, see the following resources:

- AWS website: [Global Infrastructure(opens in a new tab)](https://aws.amazon.com/about-aws/global-infrastructure/)
- [(opens in a new tab)](https://infrastructure.aws/)AWS whitepaper: [AWS Global Infrastructure Documentation(opens in a new tab)](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html)
- AWS website: [AWS Regions and Availability Zones(opens in a new tab)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- AWS reference guide: [AWS Service Endpoints(opens in a new tab)](https://docs.aws.amazon.com/general/latest/gr/rande.html)
- AWS website: [AWS Regional Services(opens in a new tab)](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)
- AWS developer guide: [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)