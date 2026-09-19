# Email Priority Triage Workflow

An n8n workflow template for classifying incoming Gmail messages and drafting priority alerts.

## Implemented flow

Gmail polling -> field extraction -> OpenAI classification -> JSON parsing -> importance condition -> Gmail notification node.

The export is **inactive**, has no credential bindings or recipient address, and contains no pinned email payload. Model output must parse as a JSON object or the workflow fails before the alert node. It is a template, not evidence of a deployed monitoring service.

## Configure and test

1. Import `AI Critical Email Alert System.json` into n8n, keeping it inactive.
2. Connect your own Gmail and OpenAI credentials through n8n's credential store.
3. Set an approved alert recipient and review the model/prompt and If condition.
4. Test with artificial messages covering important, normal, irrelevant and malformed-model-output cases.
5. Inspect each node's data and confirm the destination before enabling scheduled execution.

No email was sent and no workflow was activated during this portfolio review. Runtime integration has not been tested in an n8n instance. Email content sent to a model needs the mailbox owner's authorization. Prompt injection, false classifications, duplicate alerts and delivery failures require further controls.

## Positioning

Supporting automation project: JSON handling, API orchestration and workflow logic. Minute-based polling is not real-time processing. There is no measured response-time saving or validated classification accuracy, so those outcomes are not claimed.
