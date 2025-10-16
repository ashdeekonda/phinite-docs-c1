---
title: "Agent Prompt"
description: "Master prompt engineering for AI agents with structured instructions, examples, and debugging techniques."
---

## Prompt engineering fundamentals

The agent prompt is the foundation of your AI agent's behavior. A well-crafted prompt defines the agent's personality, capabilities, and decision-making logic. Poor prompts lead to inconsistent, irrelevant, or incorrect responses.

### Prompt structure template

```markdown
# Role Definition
You are a [specific role] that [primary function].

# Context
You work in a [business context] where [relevant background information].

# Capabilities
You can:
- [Capability 1]
- [Capability 2]
- [Capability 3]

# Instructions
When processing requests:
1. [Step 1]
2. [Step 2]
3. [Step 3]

# Examples
Input: [Sample input]
Output: [Expected output format]

# Constraints
- Do not [restriction 1]
- Always [requirement 1]
- Never [prohibition 1]

# Output Format
Respond in [specific format] with [required elements].
```

## Access control and permissions

<Warning>
Prompt editing requires "Developer" role or higher. Users with "Tester" or "Viewer" roles can only view prompts but cannot modify them.
</Warning>

### Role-based prompt access
- **SuperAdmin/Admin**: Full access to all prompt features including AI refinement
- **Developer**: Can edit prompts and use refinement tools; changes require approval for production
- **Tester**: Read-only access for testing purposes
- **Viewer**: Limited to viewing published prompts only

## Creating effective prompts

### Step-by-step prompt creation

<Steps>
<Step title="Define the agent's role">
  Clearly specify what the agent is and what it does.
  
  **Good example**:
  ```markdown
  You are a customer service specialist for an e-commerce platform. 
  Your primary role is to help customers with order-related inquiries, 
  returns, and product questions.
  ```
  
  **Poor example**:
  ```markdown
  You are helpful.
  ```
</Step>

<Step title="Provide context and background">
  Give the agent relevant business context and domain knowledge.
  
  **Good example**:
  ```markdown
  You work for TechStore, an online electronics retailer. We sell 
  computers, phones, accessories, and home electronics. Our return 
  policy allows 30-day returns for most items, except software and 
  personalized products.
  ```
</Step>

<Step title="Define capabilities and limitations">
  Clearly state what the agent can and cannot do.
  
  **Good example**:
  ```markdown
  You can:
  - Look up order status and tracking information
  - Process return requests and issue refunds
  - Answer product questions and provide recommendations
  - Escalate complex issues to human agents
  
  You cannot:
  - Process payments or update billing information
  - Modify orders that have already shipped
  - Access customer account passwords
  ```
</Step>

<Step title="Include examples and patterns">
  Provide sample interactions to guide the agent's responses.
  
  **Good example**:
  ```markdown
  Example 1:
  Customer: "Where is my order?"
  You: "I'd be happy to help you track your order. Could you please 
  provide your order number or the email address used for the purchase?"
  
  Example 2:
  Customer: "I want to return this item"
  You: "I can help you with that return. To get started, I'll need 
  your order number and the reason for the return."
  ```
</Step>

<Step title="Set output format requirements">
  Specify how the agent should structure its responses.
  
  **Good example**:
  ```markdown
  Always structure your responses as follows:
  1. Acknowledge the customer's request
  2. Ask for any required information
  3. Provide the solution or next steps
  4. Offer additional help if appropriate
  
  Use a friendly, professional tone. Keep responses concise but complete.
  ```
</Step>
</Steps>

## AI-powered prompt refinement

### Using the built-in refinement tool

<Steps>
<Step title="Access refinement">
  In the Inspector's Details tab, click "Refine with AI" after writing your initial prompt.
</Step>

<Step title="Review suggestions">
  The AI will analyze your prompt and suggest improvements for:
  - Clarity and specificity
  - Missing context or examples
  - Better structure and organization
  - More precise instructions
</Step>

<Step title="Apply or customize">
  Choose to apply all suggestions, select specific improvements, or manually edit the refined version.
</Step>
</Steps>

### Refinement best practices

<Tip>
Use refinement as a starting point, not a final solution. Always review and customize AI suggestions to match your specific use case.
</Tip>

- **Iterate multiple times**: Refine prompts based on actual agent performance
- **Test with real scenarios**: Use actual customer queries to validate prompt effectiveness
- **Monitor performance**: Track response quality and adjust prompts accordingly
- **Version control**: Keep track of prompt changes and their impact on performance

## Debugging prompt issues

### Common prompt problems and solutions

<AccordionGroup>
<Accordion title="Agent gives irrelevant responses">
**Symptoms**: Agent responds to queries but answers are off-topic or unhelpful

**Debugging steps**:
1. Check if the prompt clearly defines the agent's role and scope
2. Verify that examples match the types of queries you expect
3. Review the context section for missing business information
4. Test with sample queries to identify gaps

**Sample debugging code**:
```javascript
// Test prompt effectiveness
const testQueries = [
  "What is your return policy?",
  "How do I track my order?",
  "Can I cancel my order?",
  "What are your business hours?"
];

// Each query should produce relevant, helpful responses
```

**Resolution**: Add more specific role definition, relevant examples, and business context
</Accordion>

<Accordion title="Agent ignores instructions">
**Symptoms**: Agent doesn't follow specific instructions or constraints

**Debugging steps**:
1. Check if instructions are clear and unambiguous
2. Verify that constraints are explicitly stated
3. Review the examples to ensure they demonstrate desired behavior
4. Test with edge cases to identify instruction gaps

**Sample debugging code**:
```javascript
// Test instruction compliance
const constraintTests = [
  "Can you process a refund?", // Should ask for order details
  "What's my password?", // Should refuse and redirect
  "Cancel my order", // Should check if order can be cancelled
];

// Verify agent follows all constraints
```

**Resolution**: Make instructions more explicit, add negative examples, and strengthen constraints
</Accordion>

<Accordion title="Inconsistent response format">
**Symptoms**: Agent responses vary in structure and format

**Debugging steps**:
1. Check if output format requirements are clearly specified
2. Verify that examples demonstrate the desired format
3. Review the prompt for conflicting format instructions
4. Test with multiple queries to identify format inconsistencies

**Sample debugging code**:
```javascript
// Test response format consistency
const formatTests = [
  "Help me with my order",
  "I want to return something",
  "What products do you sell?"
];

// All responses should follow the same structure
```

**Resolution**: Clarify output format requirements and provide consistent examples
</Accordion>

<Accordion title="Agent asks for unnecessary information">
**Symptoms**: Agent requests information that's not needed for the task

**Debugging steps**:
1. Review the prompt for overly broad information requests
2. Check if examples demonstrate efficient information gathering
3. Verify that the agent understands what information is actually needed
4. Test with scenarios where minimal information should suffice

**Sample debugging code**:
```javascript
// Test information efficiency
const efficiencyTests = [
  "Track order 12345", // Should only need order number
  "Return item ABC", // Should only need order details
  "Business hours", // Should not need any customer info
];

// Verify agent asks only for necessary information
```

**Resolution**: Streamline information requirements and provide examples of efficient interactions
</Accordion>
</AccordionGroup>

## Advanced prompt techniques

### Chain-of-thought prompting
```markdown
When processing a request, think through the problem step by step:

1. First, identify what the customer is asking for
2. Determine what information you need to help them
3. Consider any constraints or limitations
4. Provide a clear, helpful response
5. Offer additional assistance if appropriate
```

### Few-shot learning
```markdown
Here are examples of how to handle different types of requests:

Example 1 - Order Status:
Customer: "Where is my order?"
You: "I'd be happy to help you track your order. Could you please provide your order number?"

Example 2 - Return Request:
Customer: "I want to return this item"
You: "I can help you with that return. To get started, I'll need your order number and the reason for the return."

Example 3 - Product Question:
Customer: "Do you have this item in stock?"
You: "I can check our inventory for you. Could you please provide the product name or SKU?"
```

### Role-playing and persona
```markdown
You are Sarah, a friendly and knowledgeable customer service representative 
with 5 years of experience helping customers with their orders. You're known 
for being patient, thorough, and always going the extra mile to help customers 
resolve their issues.

Your personality traits:
- Empathetic and understanding
- Detail-oriented and accurate
- Proactive in offering solutions
- Professional but approachable
```

## Testing and validation

### Prompt testing checklist

<Check>
- [ ] Role is clearly defined and specific
- [ ] Context includes relevant business information
- [ ] Capabilities and limitations are explicitly stated
- [ ] Examples demonstrate desired behavior
- [ ] Output format is clearly specified
- [ ] Constraints are unambiguous
- [ ] Prompt handles edge cases appropriately
- [ ] Response quality meets business requirements
</Check>

### Performance monitoring

- **Response relevance**: Track how often responses directly address customer queries
- **Information efficiency**: Monitor how quickly agents gather necessary information
- **Constraint compliance**: Ensure agents follow all specified rules and limitations
- **Customer satisfaction**: Measure customer feedback on agent interactions

## Integration with other components

### RAG integration
- **[Knowledge Base](/flowgen/agent-block/rag)**: Ground prompts with enterprise data
- **[Data Sources](/flowgen/rag-management)**: Connect prompts to relevant information sources

### Tool integration
- **[Tools](/flowgen/agent-block/tools)**: Enable prompts to trigger external actions
- **[DevStudio](/devstudio/overview)**: Create custom tools for specific prompt needs

### Variable management
- **[Variables](/flowgen/agent-block/variables)**: Use captured data to personalize prompts
- **[Decision Logic](/flowgen/connections/conditional-edges)**: Create dynamic prompts based on workflow state

## Best practices summary

1. **Start specific**: Define clear roles and boundaries from the beginning
2. **Iterate based on data**: Use actual performance metrics to refine prompts
3. **Test thoroughly**: Validate prompts with real-world scenarios
4. **Monitor continuously**: Track performance and adjust as needed
5. **Document changes**: Keep track of prompt versions and their impact
6. **Collaborate**: Get feedback from stakeholders and end users
7. **Stay current**: Update prompts as business requirements evolve
