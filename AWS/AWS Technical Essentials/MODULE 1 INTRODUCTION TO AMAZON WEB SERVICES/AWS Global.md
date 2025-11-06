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
	- Availability
	- Compliance

