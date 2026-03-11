This project implements a Routing Agentic Workflow. Instead of a single AI trying to do everything, this system uses a "Front Desk" agent that identifies the user's intent and 
routes it to the correct specialist.

**The Architecture**
I’ve designed this using a Modular Multi-Agent approach. Each agent has its own specific "Hands" (Tools) and "Brain" (Instructions).

1. The Router (The Voice/A2A)
The Router Team acts as the intelligent switchboard. It evaluates the incoming query and decides which specialized agent is best equipped to handle it.

Mode: route

Decision Logic: Technical vs. Sales vs. General Inquiry.

2. The Specialists (The Hands/MCP)
Each specialist agent is isolated. They only know their own role and only have access to their own specific Tools (Context).

    Agent                Responsibility                                Tool (The Context)
Tech Support          "Fixes crashes, login, and freezing."          TechnicalSupportTool
Sales Agent           "Handles pricing, costs, and discounts."            SalesTool
General Inquiry       "Handles hours, location, and contact."          GeneralInfoTool

**How the Workflow Operates**
When a query enters the system, it follows this 3-step process:

* Intent Classification: The Router analyzes the prompt.

Example: "Do you have discounts?" → Sales Intent.

* Delegation (A2A): The Router "wakes up" only the Sales Agent. The other agents remain idle, saving computation and reducing noise.

* Tool Execution (MCP): The Sales Agent uses its SalesTool to look up the specific discount data and provides a direct, two-line response.

**Key Advantages**
1. Zero Confusion: Because the Tech Agent never sees Sales questions, there is zero risk of it giving the wrong pricing information.

2. Plug-and-Play: To add a new capability (like "Refunds"), you simply create a RefundAgent with a RefundTool and add it to the Router's members.

3. Direct Answers: By giving the agents strict instructions to provide "short answers in less than two lines," the workflow ensures a fast and efficient user experience.
