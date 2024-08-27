**Executive Summary: Technical Support Analysis Report**

**Introduction** 

This report provides a comprehensive analysis of technical support operations based on the dataset provided. The objective is to examine key performance indicators (KPIs) related to ticket volume, content, resolution, and overall performance, in line with the focus areas outlined in the brief. The report will highlight trends in ticket creation, resolution times, agent performance, and adherence to Service Level Agreements (SLAs).

**About The Dataset**

The dataset used for this analysis was the Onyx DataDNA Monthly Challenge dataset for May 2024, provided on the website. This challenge is designed to help explore and understand the functioning of a technical support center by focusing on key performance indicators (KPIs) relevant to the volume, content, and resolution of support tickets. The insights gained from this analysis can be used to improve support efficiency, customer satisfaction, and overall service quality.

The dataset contains 2,330 entries and 22 columns related to technical support ticket management. Here are the columns:

*Status*:Ticket Status in Support Pipeline. (Open: a new ticket awaiting processing, In Progress: Currently being addressed by an agent, Resolved: Solution has been provided. Closed: Customer has confirmed the ticket's closure.)

*Ticket ID:* Unique Ticket Number.

*Source:* Channel of Request (chat, phone, email).

*Priority:* Ticket Urgency (low, medium, high).

*Support Level:* Ticket Difficulty Level (Tier 1, Tier2).
*Product group:* Product group to which the request pertains.

*Topic:* Subject matter of the customer's inquiry.

*Agent Group:* Agent group to whom the agent belongs (1st level support, 2nd level support).

*Agent Name:* Agent currently handling the ticket.

*Created time:* Timestamp indicating when the ticket was received.

*Expected SLA to first response:* Deadline for providing the initial response.

*First response time:* Timestamp of the initial response.

*SLA For first response:* First Response Compliance (Within SLA, SLA Violated).

*Expected SLA to resolve:* Deadline for resolving the ticket.

*Resolution time:* Timestamp of ticket resolution.

*SLA For Resolution:* Resolution Compliance (Within SLA, SLA Violated).

*Close time:* Timestamp of ticket closure.

*Agent interactions:* Total count of agent interactions for each ticket.

*Survey results:* Customer Satisfaction Rating: Feedback score on a scale of 1 to 5.

*Country:* Country of origin for the customer creating the ticket.	

*Latitude:* Country Coordinates: Latitude

*Longitude:* Country Coordinates: Longitude

**Data Cleaning and Transformation ETL**

The dataset was imported into Power BI as an Excel workbook and then loaded into Power Query for further processing. First, I promoted the first row to headers, and then split columns containing both date and time into separate date and time columns. A new column for Rating was created, where star symbols were assigned based on the rating scores. Several columns were renamed to better reflect the data they contained, and a calendar table was created using the following DAX expression:  ![here](DAXcode)

Additionally, numerous measures were created to enable a comprehensive analysis. To keep the report concise, I won’t delve into the details of each measure, here are a few of them : ![here](DAXcode)


1. **Ticket Volume Trends:**
   

![](TS1.jpg)


Daily, Weekly, and Monthly Volumes: The analysis reveals that ticket volumes are higher on weekdays compared to weekends, with the majority of tickets being created during standard work hours. A significant drop in ticket volumes is observed during weekends and non-working hours, indicating a peak in ticket creation during regular business days and times.

Ticket Distribution: The distribution of tickets is skewed towards standard work hours, with 41.4% of tickets created during these times. Non-work hours see a reduced ticket volume, with late and early work hours contributing to only 16.9% of total tickets.

2. **Trends in Ticket Topics:**
   
![](TS2.jpg)

3. **Channel Comparison:**

 The majority of tickets are raised via email (53%), followed by chat (36.5%) and phone (10.6%). However, chat tickets have the highest SLA violation rate, suggesting that real-time support channels might need further optimization to meet SLA targets.

![](TS3.jpg)

First Response and Resolution Times: While 86.65% of tickets met the SLA for first response, the resolution SLA adherence is lower, with only 66.39% of tickets resolved within the target SLA. This indicates a need for improvement in resolution times, especially for high-priority tickets.

SLA Adherence: The overall SLA adherence for first responses stands at 86.65%, with 13.35% of tickets violating the SLA. The resolution SLA is violated more frequently, with 33.61% of tickets failing to meet the target time.

Tickets are predominantly related to "Product setup" and "Pricing and licensing," followed by "Feature requests" and "Bug reports." This suggests a strong demand for support in product onboarding and pricing-related queries.

4. **Performance Metrics:**

![](TS5.jpg)

Operational Efficiency: Topics like Purchasing and Invoicing show relatively low interaction counts and moderate resolution times, indicating a potential benchmark for efficiency that could be replicated across other categories.

Training Opportunities: The number of interactions required for "Other" topics suggests a need for either better categorization of these tickets or additional resources for agents to handle unique or complex queries more effectively.

Agent Performance: Agents like Nicola Wane and Sheela Cutten have high ticket volumes with commendable SLA adherence. However, Kristos Westoll and Adolpho Messingham show higher SLA violations, indicating areas for performance improvement. The average rating of agent interactions varies, with higher ratings typically correlating with better SLA adherence.

**Conclusion:**

 At the executive level, the focus should be on improving SLA adherence, particularly for ticket resolution times, and optimizing support channels to reduce SLA violations. Efforts should be made to address the high volume of tickets related to "Product setup" and "Pricing and licensing," as these areas significantly impact customer satisfaction. Regular monitoring of agent performance and targeted training for underperforming agents can help enhance overall efficiency and service quality.

**Recommendations:**

Enhance SLA Adherence: Implement stricter monitoring and automated alerts to ensure timely responses and resolutions, particularly for high-priority tickets.

Optimize Support Channels: Invest in improving chat support to reduce SLA violations and enhance customer experience in real-time interactions.

Agent Training and Development: Provide targeted training for agents with higher SLA violation rates and focus on areas where tickets are most frequent, such as product setup.







