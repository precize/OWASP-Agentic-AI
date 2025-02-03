# AAI011: Agent untracability

### Description

AI agents' autonomy and dynamic role inheritance complicate traceability and forensic analysis. Agents trigger actions which in turn can trigger other tools using different identities to perform actions. The ability of agents to also temporarily assume permissions from multiple users or systems blurs accountability, making it difficult to pinpoint the origin of actions, especially during malicious activity. Inconsistent logging and ephemeral roles hinder effective auditing, slowing incident response and investigation. Untraceability due to ephemeral role inheritance AI Agents perform tasks autonomously. They often inherit roles and permissions from the users that run them. Due to the ephemeral nature of activities performed as well as many roles inherited to do disparate tasks, it's often hard to trace an activity back to the source. This makes it hard to do forensics when malicious activity happens. All these lead to issues with tracability and accountability, which are the bedrock for AI security and governance.

* **Trace cleanup** occurs when agents can clean up traces and logs even as they take certain actions
* **Exploiting autonomy for untracability** due to the complicated management of permissions in the Agentic world, including role inheritence and pipeline triggers where tools get triggered by upstream tools, which may have different identities and roles, making it hard to trace the actual owner and holding the owner accountable.

### Common Examples of Vulnerability

1. Attackers use malicious agents that trigger unauthorized tasks by downstream tools
2. Attacker uses an existing agent to do malicious tasks and cleans up traces so forensics becomes hard
3. Attacker uses the existing agent setup but exploits the fact that tracability and accountability in an Agentic system is almost impossible to do
4. Such untracability vulnerability has been given as an excuse by corporations to say that they are not liable to actions by AI Agents (which has not stood in the court of law).
5. Agent has or escalates permissions to clean up traces

### Prevention and Mitigation Strategies

1. Implement strict tracability:
   - Create logs and traces for every agent action
   - Have clear corelation of every agent action
   - Input validation for agents
   - Validate traces for known actions
   - Have cler ownership and accountability of an agent

2. Downstream tools tracability
   - Corelate downstream tool actions to upstream agents 
   - Hold upstream agent accountable for downstream tool actions

3. Check Agent supply chain:
   - Validate agent source
   - Validate agent working
   - Validate agent permissions

4. Use sidecar agents
   - Sidecar agents to validate agent behavior
   - Clear separation of sidecar and core agent
   - Disallow core agent permissions to traces

### Example Attack Scenarios

1. An attacker systematically takes excess permissions on a system and cleans up traces of such permissions (this is a known exploit with OpenInterpreter agent)

2. A sophisticated attack targets an agent's supply chain to put a malicious agent which does not put in right traces or puts in malicious traces to make it hard to do forensics.

### Reference Links

