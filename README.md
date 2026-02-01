# Gronite_Ops
The Autonomous SRE with RAG, MCP and Granite

orchestrate env add -n sre -u https://api.ca-tor.watson-orchestrate.cloud.ibm.com/instances/47a56683-0dd6-48a4-af51-2928ad773514 --type ibm_iam --activate
#
orchestrate tools import -k langflow -f sre.json

## Problems and Solutions
The Problem In modern enterprise environments, Site Reliability Engineers (SREs) are overwhelmed by "Toil"—the repetitive, manual work of triaging system incidents. When a service latency spike or a 504 Gateway Timeout occurs, an engineer must manually correlate messy logs with thousands of pages of static documentation, such as the Google SRE handbook. This manual context-switching leads to high Mean Time To Resolution (MTTR), increased downtime costs, and human error during high-pressure outages.

The Solution SRE Sentinel is an agentic AI solution built on IBM watsonx Orchestrate that transforms passive documentation into active, autonomous diagnostics. Our solution empowers SREs by providing a single, intelligent interface that bridges the gap between Static Industry Knowledge and Dynamic System Action.

## Agent Usage as 
Our project utilizes Agentic AI through a multi-skill orchestration pattern in watsonx Orchestrate.

    The Orchestrator: Uses the ReAct style to break down user requests into logical steps.

    Knowledge Agent: A RAG-based skill indexed with the Google SRE handbook, providing the 'brain' or theoretical framework for diagnostics.

    Diagnostic Agent (Langflow Skill): An autonomous tool imported via the ADK CLI that serves as the 'hands' of the system. It parses system logs to identify error patterns (like 504 timeouts) and confirms if they match the retrieved documentation. These agents work together by sharing context: the Knowledge Agent identifies what to look for, and the Langflow skill confirms if it is happening, delivering a unified, actionable resolution plan to the user."
