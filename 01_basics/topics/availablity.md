# System Design

## What is Availability?
Availability is the percentage of time a system remains operational and accessible when it's needed. It reflects how resilient and reliable a system is under normal or adverse conditions.

### Key Formula
matlab

Availability (%) = (Uptime / (Uptime + Downtime)) * 100
Example:
If a system was down for 10 minutes in a month (43,200 minutes),

Availability = (43190 / 43200) * 100 ≈ 99.98%
## Nines of Availability
Availability (%)	Downtime per Year	Downtime per Month	Nickname
99%	                ~3.65 days	        ~7.2 hours	        Two nines
99.9%	            ~8.76 hours     	~43.8 minutes	    Three nines
99.99%          	~52.6 minutes	    ~4.38 minutes	    Four nines
99.999%	            ~5.26 minutes	    ~26.3 seconds	    Five nines

## Factors That Affect Availability
🔄 Redundancy: Multiple servers/components to avoid single points of failure.

💾 Failover: Auto-switching to backup systems during failures.

🔌 Power and Network Stability: Ensures infrastructure uptime.

🛠️ Monitoring and Alerts: Early detection of issues.

🔁 Auto-healing: Self-repairing mechanisms (e.g., container restarts).

🧪 Testing: Chaos testing, load testing for fault tolerance.

## Availability vs Reliability
Attribute	Availability	             Reliability
Focus	   System is up and running	     System runs without failures
Scope	   Short-term accessibility    	Long-term correctness & consistency
Example	   API is reachable	            API returns the correct response every time

## Techniques to Improve Availability
1. Load Balancing
Distributes traffic to prevent server overload.

2. Health Checks
Used by load balancers to only send traffic to healthy servers.

3. Replication
Multiple copies of services/databases reduce downtime risk.

4. Auto-Scaling
Adds/removes resources dynamically based on demand.

5. Failover Systems
Backup servers take over when a primary server fails.

## Real-World Scenarios
Amazon: Uses highly available distributed systems with fallback zones.

Netflix: Uses chaos engineering to simulate and test system failures.

Banking Systems: Require five nines (99.999%) due to critical services.

## Summary
Availability ensures that your system is accessible when users need it. Through replication, monitoring, and failover strategies, you can design systems that stay up even during unexpected issues.