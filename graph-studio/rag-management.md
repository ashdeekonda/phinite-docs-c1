---
title: "RAG Management"
description: "Manage data sources and collections used to ground agents."
---

## Overview

RAG enables agents to reference enterprise knowledge. You'll attach curated collections to each agent in the Inspector.

## Adding Data Sources

<Steps>
<Step title="Open Data Sources">
  Go to your workspace data sources section (admin area).
</Step>
<Step title="Add a source">
  Provide connection details and scope.
</Step>
<Step title="Validate">
  Confirm connectivity and indexing if required.
</Step>
</Steps>

<Tip>
Use meaningful names; agents display source and item names in the RAG selector.
</Tip>

## Creating Collections

<Steps>
  <Step title="Create a collection">
    <Frame>
  <img src="/images/collection.png" alt="Descriptive alt text" />
</Frame>

    Define a collection relevant to a domain or task.
  </Step>
  <Step title="Add items">
        <Frame>
  <img src="/images/uploaded.png" alt="Descriptive alt text" />
</Frame>
    
    Include documents or entries from connected sources.
  </Step>
  <Step title="Review relevance">
    Keep collections focused and high-signal for better grounding.
  </Step>
</Steps>

## Referencing Collections in Agents

<Steps>
  <Step title="Open the agent node">
    <Frame>
      <img
        src="/images/open-the-agent-block-1.png"
        alt="Step 1 Pn"
        lightAlt="open the agent block"
        darkAlt="Step 1 Pn"
        className="dark:hidden"
      />
      <img
        src="/images/step-1.png"
        alt="Step 1 Pn"
        lightAlt="open the agent block"
        darkAlt="Step 1 Pn"
        className="hidden dark:block"
      />
    </Frame>

    Select the agent and open the RAG tab.
  </Step>
  <Step title="Select data source and items">
    <Frame>
      <img
        src="/images/select-a-collection.png"
        alt="Step 2 Pn"
        lightAlt="select a collection"
        darkAlt="Step 2 Pn"
        className="dark:hidden"
      />
      <img
        src="/images/step-2.png"
        alt="Step 2 Pn"
        lightAlt="select a collection"
        darkAlt="Step 2 Pn"
        className="hidden dark:block"
      />
    </Frame>

    Choose a source and add the most relevant items (or collection) for this task.
  </Step>
  <Step title="Save and test">
    <Frame>
      <img
        src="/images/choose-a-data-source-2.png"
        alt="Step 3 Pn"
        lightAlt="data source items"
        darkAlt="Step 3 Pn"
        className="dark:hidden"
      />
      <img
        src="/images/step-3.png"
        alt="Step 3 Pn"
        lightAlt="data source items"
        darkAlt="Step 3 Pn"
        className="hidden dark:block"
      />
    </Frame>

    Save the configuration and test the agent on sample inputs.
  </Step>
</Steps>

<Check>
  The agent should now cite or leverage attached knowledge where appropriate.
</Check>
