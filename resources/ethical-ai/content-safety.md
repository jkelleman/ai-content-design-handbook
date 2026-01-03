# Content Safety Guidelines

A comprehensive framework for preventing harmful content and protecting users in AI-powered experiences.

## What is Content Safety?

**Content safety** = Protecting users from harmful, inappropriate, or dangerous content

**Why it's critical:**
- **User protection** - Prevent physical, emotional, financial harm
- **Trust** - Users must feel safe to engage
- **Legal compliance** - Many jurisdictions require safeguards
- **Brand reputation** - Safety incidents damage trust
- **Ethical responsibility** - Duty to protect users from harm

**AI amplifies safety risks:**
- Can generate harmful content at scale
- Lacks human judgment and context
- May not recognize nuanced harm
- Learns from potentially toxic training data
- Difficult to predict all failure modes

## Types of Harmful Content

### 1. **Violence & Threats**

**Includes:**
- Threats of violence
- Instructions for violence
- Glorification of violence
- Graphic violent content
- Self-harm content
- Weapons/explosives instructions

**Examples:**

```markdown
❌ Harmful:
"Here's how to build a [weapon]..."
"You should [harm] people who..."
"Ways to [violent act]..."

✅ Safe:
"I can't provide that information. If you're concerned about 
safety, contact local authorities."
```

**Mitigation:**
- Block weapon/violence keywords
- Don't provide harmful instructions
- Escalate threats immediately
- Provide crisis resources

---

### 2. **Hate Speech & Harassment**

**Includes:**
- Slurs and derogatory language
- Targeted harassment
- Dehumanization
- Discrimination based on protected characteristics
- Hate group content

**Examples:**

```markdown
❌ Harmful:
[Slurs, derogatory statements about groups]
"[Group] are all [negative stereotype]"
"How to harass [person/group]"

✅ Safe:
"I don't engage with content that targets or demeans people 
based on their identity."
```

**Mitigation:**
- Block hate speech patterns
- Don't engage with harassment
- Report serious incidents
- Maintain zero tolerance

---

### 3. **Self-Harm & Suicide**

**Includes:**
- Suicide instructions/encouragement
- Self-harm methods
- Pro-suicide content
- Eating disorder promotion

**Examples:**

```markdown
❌ Harmful:
"Ways to [self-harm method]"
"You should just [self-harm]"
Dismissive responses to crisis

✅ Safe:
"I'm concerned about what you shared. Please reach out for help:

• National Suicide Prevention Lifeline: 988 (US)
• Crisis Text Line: Text HOME to 741741  
• International: findahelpline.com

You don't have to face this alone."
```

**Mitigation:**
- Detect crisis keywords
- Provide immediate resources
- Escalate to crisis services
- Never dismiss or minimize

---

### 4. **Child Safety**

**Includes:**
- Child sexual abuse material (CSAM)
- Grooming behavior
- Inappropriate content involving minors
- Child exploitation

**Examples:**

```markdown
❌ Harmful:
Any content sexualizing minors
Instructions for inappropriate contact with minors
Requests for CSAM

✅ Safe:
Immediate rejection + reporting to authorities
Zero tolerance enforcement
```

**Mitigation:**
- Strictest filtering
- Report to NCMEC (National Center for Missing & Exploited Children)
- Involve legal/law enforcement
- Preserve evidence
- Zero tolerance - always escalate

---

### 5. **Sexual Content**

**Includes:**
- Explicit sexual content (when inappropriate)
- Non-consensual sexual content
- Sexual harassment
- Sexualization without consent

**Context matters:**
- Educational: ✅ Allowed
- Unsolicited/inappropriate: ❌ Blocked

**Examples:**

```markdown
❌ Harmful:
Unsolicited explicit content
Non-consensual scenarios
Sexual harassment

✅ Safe (when appropriate):
"For information about sexual health, visit [authoritative source]"
```

**Mitigation:**
- Context-aware filtering
- Age verification for adult content
- Consent mechanisms
- Report capabilities

---

### 6. **Illegal Activities**

**Includes:**
- Instructions for illegal acts
- Drug manufacturing
- Fraud/scams
- Hacking/unauthorized access
- Piracy

**Examples:**

```markdown
❌ Harmful:
"How to hack into..."
"Steps to manufacture [illegal drug]"
"Ways to commit fraud"

✅ Safe:
"I can't help with that. It's illegal and could cause serious harm."
```

**Mitigation:**
- Block illegal instructions
- Don't provide workarounds
- Legal compliance checks
- Report serious violations

---

### 7. **Medical Misinformation**

**Includes:**
- Unqualified medical advice
- Anti-vaccine misinformation
- Dangerous health claims
- Prescription drug advice
- Diagnosis attempts

**Examples:**

```markdown
❌ Harmful:
"You don't need your [medication]"
"[Unproven remedy] cures [serious disease]"
"Vaccines cause [false claim]"

✅ Safe:
"I'm not qualified to provide medical advice. For health concerns,
please consult a healthcare provider or visit [authoritative source]."
```

**Mitigation:**
- Defer to medical professionals
- Link to authoritative sources (CDC, WHO, Mayo Clinic)
- Flag medical keywords for review
- Never diagnose or prescribe

---

### 8. **Personal Information (PII/Doxing)**

**Includes:**
- Sharing others' private info
- Social security numbers
- Credit card numbers
- Home addresses
- Private contact information

**Examples:**

```markdown
❌ Harmful:
Displaying or requesting PII
"[Person]'s address is..."
Storing/exposing sensitive data

✅ Safe:
"I can't share personal information about individuals."
[Redact PII if accidentally included]
```

**Mitigation:**
- PII detection and redaction
- Never store unnecessary PII
- Privacy by design
- Encryption for sensitive data

---

### 9. **Manipulation & Deception**

**Includes:**
- Deepfake instructions
- Phishing templates
- Social engineering
- Disinformation creation
- Impersonation

**Examples:**

```markdown
❌ Harmful:
"How to create fake [credential]"
"Phishing email template"
"Impersonate [person/entity]"

✅ Safe:
"I can't help create deceptive content. For legitimate 
communication needs, I can help with honest, transparent approaches."
```

**Mitigation:**
- Block deception instructions
- Require transparency
- Watermark AI-generated content
- Disclosure requirements

## Safety Framework

### Prevention Layers

```
Layer 1: Input Filtering
  ↓ Block obviously harmful requests
  
Layer 2: Context Understanding
  ↓ Understand intent behind request
  
Layer 3: Output Filtering  
  ↓ Scan generated content for harm
  
Layer 4: Human Review
  ↓ Review flagged content
  
Layer 5: User Reporting
  ↓ Users flag harmful content
  
Layer 6: Continuous Learning
  ↓ Update filters based on incidents
```

### Safety Checks

**Before generation:**

```python
def pre_generation_safety_check(user_input):
    """Screen input before generating response"""
    
    # Category detection
    category = classify_content(user_input)
    
    if category in ['violence', 'hate', 'child_safety']:
        return {
            'allow': False,
            'reason': 'harmful_request',
            'response': get_rejection_message(category)
        }
    
    if category == 'self_harm':
        return {
            'allow': False,
            'reason': 'crisis',
            'response': get_crisis_resources()
        }
    
    if category in ['medical', 'legal', 'financial']:
        return {
            'allow': True,
            'guidance': 'add_disclaimer',
            'context': category
        }
    
    return {'allow': True}
```

**After generation:**

```python
def post_generation_safety_check(ai_output):
    """Screen output before showing to user"""
    
    # Content scanning
    safety_scan = {
        'toxicity': check_toxicity(ai_output),
        'pii': detect_pii(ai_output),
        'medical': detect_medical_advice(ai_output),
        'violence': detect_violence(ai_output),
        'hate': detect_hate_speech(ai_output)
    }
    
    # Critical issues = block immediately
    if any([
        safety_scan['violence'] > 0.8,
        safety_scan['hate'] > 0.8,
        'ssn' in safety_scan['pii'],
        'credit_card' in safety_scan['pii']
    ]):
        return {
            'allow': False,
            'reason': 'unsafe_content',
            'response': fallback_safe_response(),
            'alert': True  # Escalate for review
        }
    
    # Medium-risk = modify
    if safety_scan['pii']:
        ai_output = redact_pii(ai_output, safety_scan['pii'])
    
    if safety_scan['medical'] > 0.5:
        ai_output = add_medical_disclaimer(ai_output)
    
    return {
        'allow': True,
        'content': ai_output,
        'warnings': get_warnings(safety_scan)
    }
```

### Severity Tiers

**Tier 1 - Critical (Zero Tolerance)**
```markdown
Categories:
- Child safety / CSAM
- Credible threats of violence
- Self-harm encouragement

Response:
1. Block immediately
2. Log incident
3. Report to authorities
4. Preserve evidence
5. Escalate to legal

No exceptions.
```

**Tier 2 - High Risk**
```markdown
Categories:
- Hate speech
- Harassment
- Violence (non-imminent)
- Illegal instructions

Response:
1. Block content
2. Log incident
3. Review within 1 hour
4. Pattern analysis
5. Consider account action
```

**Tier 3 - Medium Risk**
```markdown
Categories:
- Medical advice (unqualified)
- Financial advice (risky)
- Privacy concerns
- Manipulation

Response:
1. Add disclaimers
2. Limit capabilities
3. Redirect to experts
4. Monitor patterns
```

**Tier 4 - Low Risk**
```markdown
Categories:
- Minor inaccuracies
- Tone issues
- Quality concerns

Response:
1. Log for improvement
2. User feedback
3. Continuous refinement
```

## Safety Patterns

### Pattern 1: Rejection with Explanation

```markdown
User: "How do I break into someone's account?"

❌ Don't:
[Silently fail or generic error]

✅ Do:
"I can't help with that. Accessing someone's account without 
permission is illegal and violates their privacy.

If you have a legitimate reason to access an account, use 
official account recovery processes or contact support."

Why this works:
- Clear why request is denied
- Educates user
- Offers legitimate alternatives
```

### Pattern 2: Crisis Resources

```markdown
User: "I want to end my life"

✅ Respond immediately:
"I'm concerned about what you shared. Please reach out for help 
right away:

**Immediate Support:**
• Call: 988 (Suicide & Crisis Lifeline - US)
• Text: HOME to 741741 (Crisis Text Line)
• Chat: 988lifeline.org

**International:**
• Visit: findahelpline.com

**Other resources:**
• Contact a trusted friend, family member, or therapist
• Go to your nearest emergency room
• Call emergency services (911 in US)

You deserve support. Help is available 24/7."

Additional actions:
- Flag conversation for review
- Consider user location for local resources
- Don't continue normal conversation
```

### Pattern 3: Expert Deferral

```markdown
User: "Should I stop taking my blood pressure medication?"

✅ Respond:
"I can't provide medical advice about your medication. This is 
an important health decision that requires professional guidance.

Please:
- Contact your prescribing doctor
- Call your pharmacy
- Visit an urgent care if you have concerns
- Don't stop medication without medical guidance

For general medication information, visit FDA.gov or talk to 
your healthcare provider."

Don't:
- Give opinion on medication
- Suggest alternatives
- Interpret symptoms
```

### Pattern 4: Transparency & Limitation

```markdown
User: "What's my diagnosis based on these symptoms?"

✅ Respond:
"I'm an AI assistant and not qualified to diagnose medical 
conditions. For an accurate diagnosis:

- Schedule an appointment with your doctor
- Visit an urgent care or ER if symptoms are severe
- Call your healthcare provider's nurse line

I can help you:
- Find nearby medical facilities
- Prepare questions for your doctor
- Understand general health information

But diagnosis requires a medical professional's evaluation."
```

### Pattern 5: Safeguarding Children

```markdown
Detecting child safety concerns:

If conversation involves:
- Inappropriate content about minors
- Requests for child-related inappropriate material
- Grooming patterns
- Child safety threats

Immediate response:
1. Terminate conversation
2. Log all details
3. Report to NCMEC (US): CyberTipline.org
4. Alert legal team
5. Preserve evidence
6. Follow mandatory reporting laws

Display to user:
"This conversation has ended due to safety concerns. 
This incident has been reported to appropriate authorities."
```

## Safety Implementation

### System Prompts

```markdown
SYSTEM PROMPT: Safety Guidelines

You are a helpful AI assistant. Your top priority is user safety.

NEVER provide:
- Violent instructions or threats
- Hate speech or harassment
- Self-harm methods or encouragement
- Any content involving minors inappropriately
- Illegal activity instructions
- Unqualified medical/legal/financial advice
- Others' personal information
- Deceptive content creation

ALWAYS:
- Prioritize user safety
- Provide crisis resources when needed
- Defer to human experts for high-risk topics
- Be transparent about your limitations
- Escalate safety concerns

If unsure whether content is safe, err on the side of caution.
```

### Content Filtering

**Input filtering:**

```python
class SafetyFilter:
    def __init__(self):
        self.blocked_patterns = load_blocked_patterns()
        self.ml_classifier = load_safety_model()
    
    def filter_input(self, text):
        # Pattern matching (fast)
        for pattern in self.blocked_patterns:
            if pattern.matches(text):
                return {
                    'safe': False,
                    'reason': pattern.category,
                    'method': 'pattern_match'
                }
        
        # ML classification (more nuanced)
        scores = self.ml_classifier.predict(text)
        
        if scores['violence'] > 0.9:
            return {'safe': False, 'reason': 'violence'}
        if scores['hate'] > 0.9:
            return {'safe': False, 'reason': 'hate'}
        if scores['self_harm'] > 0.8:
            return {'safe': False, 'reason': 'crisis'}
        
        return {'safe': True}
```

**Output filtering:**

```python
def filter_output(generated_text):
    """Multi-layer output safety check"""
    
    # Layer 1: Fast pattern check
    if contains_blocked_patterns(generated_text):
        return fallback_response(), 'blocked_pattern'
    
    # Layer 2: PII detection
    pii = detect_pii(generated_text)
    if pii:
        generated_text = redact_pii(generated_text, pii)
    
    # Layer 3: Toxicity scoring
    toxicity = score_toxicity(generated_text)
    if toxicity > 0.8:
        return fallback_response(), 'high_toxicity'
    
    # Layer 4: Fact checking (for critical domains)
    if is_medical_or_safety_advice(generated_text):
        if not verify_with_knowledge_base(generated_text):
            generated_text = add_disclaimer(generated_text)
    
    return generated_text, 'passed'
```

### Monitoring & Alerts

**Real-time monitoring:**

```python
class SafetyMonitor:
    def __init__(self):
        self.alert_thresholds = {
            'tier1_incidents': 1,  # Alert on any Tier 1
            'tier2_incidents_per_hour': 5,
            'pattern_spike': 3x_baseline
        }
    
    def check_and_alert(self, incident):
        # Tier 1: Immediate alert
        if incident.tier == 1:
            send_alert(
                urgency='CRITICAL',
                channels=['on_call', 'slack', 'email'],
                message=f'Tier 1 safety incident: {incident.id}'
            )
            log_to_security_system(incident)
        
        # Pattern detection
        recent_incidents = get_recent_incidents(hours=1)
        if len(recent_incidents) > self.alert_thresholds['tier2_incidents_per_hour']:
            send_alert(
                urgency='HIGH',
                channels=['slack', 'email'],
                message=f'Safety incident spike: {len(recent_incidents)} in past hour'
            )
```

**Dashboard metrics:**

```markdown
=== Safety Dashboard ===

Last 24 Hours:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Tier 1 incidents:     0 ✓
Tier 2 incidents:     3 (within normal range)
Tier 3 incidents:     45
Total blocked:        2,847
Block rate:           2.1%

Categories:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Violence:             0
Hate:                 1 (reviewed, resolved)
Self-harm:            2 (crisis resources provided)
Medical:              8 (disclaimers added)
PII:                  15 (redacted)
Illegal:              1 (blocked)

Trends:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Incidents stable vs last week
✓ No pattern spikes detected
✓ Response time < 5min (target < 15min)

Action Items:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• Review 3 flagged Tier 2 incidents
• Update medical disclaimer wording
• Weekly team review scheduled
```

## User Reporting

### Reporting Mechanism

**Make it easy to report:**

```markdown
On every AI response:

[Response content]

Was this helpful?  👍  👎

⚠️ Report safety concern
```

**Reporting form:**

```markdown
Report Safety Concern

What's the issue? (select all that apply)
☐ Harmful or dangerous content
☐ Hateful or discriminatory
☐ Sexually explicit
☐ Promotes illegal activity
☐ Privacy violation
☐ Other concern

Additional details (optional):
[Text box]

[Submit Report]  [Cancel]

Your report is anonymous and helps keep everyone safe.
```

### Report Response

**User sees:**
```markdown
✓ Thank you for your report

We take safety seriously. This content has been flagged 
for immediate review by our safety team.

If you're in immediate danger, please contact emergency 
services or use these resources:
• Crisis support: 988
• Emergency: 911
```

**Team receives:**
```markdown
SAFETY REPORT #2847

Timestamp: 2024-03-15 14:32 UTC
Reporter: user_abc123 (anonymized)
Issue: Harmful or dangerous content
Content ID: msg_xyz789

[Content of reported interaction]

Priority: HIGH (auto-escalated based on keywords)
Assigned to: Safety team on-call
SLA: Review within 1 hour

[Review] [Block Content] [Contact User] [Escalate]
```

## Safety Training

### For Content Teams

```markdown
Safety Training (Required)

Module 1: Why Safety Matters (15min)
- Real impact on users
- Legal requirements
- Ethical obligations

Module 2: Recognizing Harm (30min)
- Types of harmful content
- Edge cases and gray areas
- Cultural context

Module 3: Response Protocols (30min)
- What to do for each tier
- Escalation procedures
- Crisis resources

Module 4: Prevention (15min)
- Safety-first design
- Building safeguards
- Testing for safety

Test: (15min)
- Scenario-based questions
- Pass rate: 90%

Recertification: Annually
```

### For AI Systems

```markdown
Safety Guidelines in Training:

1. Training data curation
   - Remove harmful content
   - Diverse, safe examples
   - Human-reviewed

2. Safety demonstrations
   - Show correct rejections
   - Model appropriate responses
   - Include crisis resources

3. Reinforcement learning
   - Reward safe outputs
   - Penalize harmful content
   - Human feedback loop

4. Red team testing
   - Adversarial prompts
   - Edge cases
   - Failure mode discovery
```

## Crisis Resources

### Global Crisis Lines

```markdown
**United States:**
- Suicide & Crisis Lifeline: 988
- Crisis Text Line: Text HOME to 741741
- SAMHSA Helpline: 1-800-662-4357

**International:**
- International Association for Suicide Prevention: iasp.info
- Befrienders Worldwide: befrienders.org
- Crisis Text Line (global): crisistextline.org

**Specialized:**
- Domestic Violence: TheHotline.org or 1-800-799-7233
- Child Abuse: ChildHelp.org or 1-800-422-4453
- LGBTQ+ Youth: TrevorProject.org or 1-866-488-7386
- Veterans: VeteransCrisisLine.net or 988 (press 1)
- Substance Abuse: 1-800-662-HELP (4357)

**Medical:**
- Poison Control: 1-800-222-1222
- Emergency: 911 (US/Canada)
```

### How to Present Resources

**✅ Do:**
```markdown
- Provide multiple options (call, text, chat)
- Include international resources
- Show specialized resources when relevant
- Emphasize 24/7 availability
- Be direct and compassionate
- Include emergency services
```

**❌ Don't:**
```markdown
- Only provide one option
- Assume user location
- Make them search for help
- Continue normal conversation
- Minimize the situation
- Give advice instead of resources
```

## Safety Incident Retrospective

After any Tier 1 or Tier 2 incident:

```markdown
Safety Incident Retrospective

Incident ID: [ID]
Date: [Date]
Severity: [Tier 1-4]

What Happened:
[Detailed description]

Impact:
- Users affected: [Number/description]
- Harm caused: [Assessment]
- Response time: [Time]

Root Cause:
[Why did this happen?]

Prevention:
What could have prevented this?
- [ ] Better filtering
- [ ] Updated guidelines
- [ ] Training gaps
- [ ] Technical issues

Response:
How did we do?
- [ ] Detected quickly
- [ ] Responded appropriately
- [ ] Escalated correctly
- [ ] Documented fully

Improvements:
1. [Immediate action taken]
2. [Short-term fix]
3. [Long-term prevention]

Follow-up:
- Review date: [Date]
- Assigned to: [Team]
```

## Legal & Compliance

### Mandatory Reporting

**Know your obligations:**

```markdown
US Requirements:
- Child abuse: Mandatory reporting in all states
- CSAM: Report to NCMEC CyberTipline
- Credible threats: May require police notification
- Healthcare (HIPAA): Special protections

International:
- GDPR: Data breach notification (72 hours)
- Australia: eSafety Commissioner reporting
- UK: Ofcom online safety requirements
- Varies by jurisdiction - consult legal
```

### Platform Obligations

```markdown
Section 230 (US):
- Good faith content moderation protected
- Must have mechanisms to address illegal content

EU Digital Services Act:
- Risk assessment required
- Transparency reports
- User reporting mechanisms
- Illegal content removal

Age-appropriate design:
- COPPA (US): Children under 13
- UK Age Appropriate Design Code
- GDPR: Children's data protection
```

## Safety Checklist

### Pre-Launch

- [ ] Safety guidelines defined
- [ ] Filtering implemented (input & output)
- [ ] Escalation procedures documented
- [ ] Crisis resources integrated
- [ ] PII detection active
- [ ] Red team testing completed
- [ ] Safety metrics dashboard ready
- [ ] Team trained on protocols
- [ ] Legal review completed
- [ ] Reporting mechanism live
- [ ] On-call rotation established
- [ ] Incident response plan ready

### Ongoing

**Daily:**
- [ ] Review flagged content
- [ ] Check safety alerts
- [ ] Monitor incident patterns

**Weekly:**
- [ ] Safety metrics review
- [ ] Incident retrospectives
- [ ] Filter effectiveness check

**Monthly:**
- [ ] Comprehensive safety audit
- [ ] Update blocked patterns
- [ ] Refresh crisis resources
- [ ] Test reporting mechanisms

**Quarterly:**
- [ ] External safety audit
- [ ] Policy updates
- [ ] Team retraining
- [ ] Legal compliance review

## Best Practices

### ✅ DO:

**Prioritize safety over features**
Better to block too much than allow harm

**Be transparent with users**
Clear why something is blocked

**Provide resources**
Help users find legitimate support

**Monitor continuously**
Safety is ongoing, not one-time

**Learn from incidents**
Every incident improves the system

**Default to caution**
If unsure, err on side of safety

### ❌ DON'T:

**Compromise on safety**
Never accept "acceptable harm"

**Ignore edge cases**
Real users encounter edge cases

**Delay crisis response**
Minutes matter in crisis situations

**Dismiss user reports**
Users are your best safety monitors

**Set and forget**
New attack vectors emerge constantly

**Go it alone**
Leverage safety tools and experts

## Related Resources

- [Ethical AI Guidelines](ethical-ai-guidelines.md)
- [Bias Detection Framework](bias-detection.md)
- [AI Content Evaluation](../../workflows/testing/ai-content-evaluation.md)
- [Crisis Resources Database](crisis-resources.md)
- [Legal Compliance Guide](../legal-compliance.md)

## Emergency Contacts

**Your organization's safety contacts:**
```markdown
Safety Team: [Contact]
On-Call Engineer: [Rotation]
Legal: [Contact]
PR/Communications: [Contact]
Executive Sponsor: [Contact]

External:
NCMEC CyberTipline: CyberTipline.org
Law Enforcement: [Local emergency number]
```

---

**Remember:** Safety is not a feature. It's a fundamental requirement. Every user interaction should be safe, respectful, and protective of human wellbeing.
