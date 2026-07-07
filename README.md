ParaIQ: An AI-Native Legal Platform
A multi-tenant legal AI platform — designed by someone who has been both the attorney using the tool and the engineer building it.

Live at app.para-iq.com

Most legal-tech platforms are case-management systems with an LLM bolted on. ParaIQ inverts that: it's an AI-native reasoning layer — research, drafting, review, and risk analysis — built on top of the workflow plumbing the industry already solved. It's designed and operated by one person who is both the legal domain expert and the full-stack engineer, and that combination shows up directly in how the AI is scoped, guarded, and evaluated.
What it does
Capability
What it does
Why it matters
Autonomous AI agents
Agents plan and execute multi-step tasks (research → draft → file-to-matter) as structured plans, not free-form chat
Every agent output passes a validation gate before it touches firm data
AI legal research
Voice- or text-triggered research memos per matter, favorability-scored, delivered to a dashboard
Attorneys get cited memos, not chat transcripts
Document review & risk
Per-document risk scoring, entity extraction, and contradiction detection across a full case file
Surfaces the cross-document inconsistencies humans miss at volume
Passive time capture
Reconstructs billable activity from system events; the attorney reviews, nothing auto-bills
Addresses a top revenue leak in small firms without trust-destroying automation
Client communication drafting
Drafts status updates and letters in the firm's voice, held behind attorney review
The review step is structural, not a checkbox
Measured RAG pipeline
Retrieval-augmented generation, evaluated with a formal scoring framework across documented runs
Pipeline changes are hypothesis-tested, including negative results
Cost-aware model routing
Lighter models for parsing and intent, stronger models for generation, with per-firm usage governance
AI spend is a governed budget line, not a surprise
Voice command layer
Dozens of commands across a chat bot, a dashboard mic, and an API — speech-to-text, intent parsing, execution
Every channel shares the same authentication and tenant scoping

Evaluation discipline
Changes to the AI pipeline are treated as experiments: hypothesis → change → measured result, with negative results kept in the record.

One run is the clearest example. A change intended to improve answer faithfulness by giving the model more source context regressed it — more context gave the model more surface to stray from. The following run recovered and surpassed the baseline by tightening the generation contract instead of loosening the inputs. The point isn't any single score; it's that the AI layer is measured rather than vibes-tested, and a result that went the wrong way was diagnosed and documented rather than buried.
Isolation you verify by attack, not by configuration
Legal data demands hard tenant isolation, and the central lesson of this project's security work is that configuration is not a guarantee.

At one point every configuration-level check on the isolation layer passed — the policies were present, correct, and enabled. Then a routine adversarial test, one tenant deliberately requesting another tenant's data, revealed a gap that no amount of config inspection would have caught. It was found and closed during a deliberately staged rollout designed for exactly that purpose.

The durable change wasn't the specific patch; it was the standard: isolation claims are now gated on an automated cross-tenant attack test — same-tenant access succeeds, cross-tenant access is denied, strict scoping holds even for privileged roles — rather than on inspecting settings. Verification by attack, not by assumption.

The rest of the security posture follows the same principle:

Fail-closed by default — an identity/tenant mismatch refuses to proceed rather than silently falling back to a default
AI output validation — model output passes a validation layer (sensitive-data redaction, harmful-content screening, schema checks) and is audit-logged
Structural review gates — AI drafts are held until a named attorney confirms review, and that confirmation is a logged, immutable event
Per-firm audit logging — every AI action, agent step, and privileged operation is recorded
What's deliberately deferred
Billing and financial infrastructure are intentionally absent. Those layers are well-served by incumbents and add no differentiation; the entire engineering bet is on the AI reasoning layer and the trust infrastructure around it.
The differentiator
Every guardrail sits where it does because the person who built it has also been the end user — knowing which AI outputs a malpractice carrier would ask about, which documents are privileged before a classifier says so, and why an attorney will never trust auto-billed time. That judgment isn't visible in any single feature; it's visible in where the guardrails are placed.


Let's connect
I'm a legal-domain expert and full-stack engineer building at the intersection of law and applied AI. If you're working on legal AI — or hiring for it — I'd welcome a conversation.

Live platform: app.para-iq.com
Email: henidt@gmail.com
LinkedIn: https://www.linkedin.com/in/maxwell-lau-86936520/



