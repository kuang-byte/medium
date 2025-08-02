# Effective Code Review Comments: Asking and Replying

Code reviews are crucial, but the way we write and respond to comments can make a huge difference. Vague or accusatory comments lead to friction, while thoughtful questions and constructive replies foster collaboration. Let's look at how to phrase review comments effectively and how to respond productively.

---

## Part 1: Asking Effectively (Phrasing Your Review Comments)

When you're reviewing code and find something that needs attention, how you phrase your comment matters. Aim for clarity, collaboration, and avoid sounding accusatory.

### Scenario: Code seems complex, fragile, or hard to maintain.

*   **Goal:** Express concern about maintainability and understand the logic without being accusatory.
*   **Avoid This Phrasing:** "This is hacky." (Vague, accusatory)
*   **Try These Phrasings:**
    *   "I'm having trouble following the logic in this section. Could we perhaps simplify it or add a comment explaining the approach? I'm concerned about long-term maintainability." *(Focuses on understanding and maintainability)*
    *   "This part seems a bit complex. Could you walk me through the reasoning here? Maybe we can find a way to make it clearer for future maintainers." *(Invites discussion, collaborative tone)*

### Scenario: Logic seems duplicated or could be reused.

*   **Goal:** Suggest abstraction or inquire about the decision not to abstract.
*   **Avoid This Phrasing:** "Why didn't you abstract this?" (Can sound demanding)
*   **Try These Phrasings:**
    *   "This logic looks potentially reusable. Do you think it makes sense to abstract it into a separate function/method now, or is it premature?" *(Opens a discussion)*
    *   "I noticed similar logic in [other location]. Could we potentially create a shared helper function to handle both cases?" *(Specific and constructive)*

### Scenario: Code is difficult to understand.

*   **Goal:** Request clarification or specific improvements for readability.
*   **Avoid This Phrasing:** "Confusing." (On a block of code - vague and unhelpful)
*   **Try These Phrasings:**
    *   "Could you walk me through this section? I'm not sure I grasp the flow." *(Requests explanation)*
    *   "Perhaps renaming `variable_foo` to something more descriptive like `user_input_buffer` could improve clarity here?" *(Specific, actionable suggestion)*

### Scenario: You think a different approach might be better.

*   **Goal:** Suggest an alternative and understand the author's choice, without demanding change.
*   **Avoid This Phrasing:** "Use Algorithm X." (Prescriptive, doesn't invite discussion)
*   **Try These Phrasings:**
    *   "Have you considered Algorithm X for this? I wonder if it might offer [specific benefit, e.g., better performance, more standard approach] in this case. What were the reasons for choosing the current algorithm?" *(Invites justification and discussion)*
    *   "Another way we could approach this is [briefly describe alternative]. What do you think about the trade-offs compared to the current implementation?" *(Offers an alternative for consideration)*

### Scenario: You spot a potential bug or edge case.

*   **Goal:** Highlight a potential issue and explore its handling.
*   **Avoid This Phrasing:** "This will crash if input is null." (Sounds accusatory, assumes certainty)
*   **Try These Phrasings:**
    *   "What's the expected behavior if `input` is null here? Should we add a check to handle that case?" *(Focuses on behavior and solutions)*
    *   "I'm wondering about the edge case where [describe scenario]. How is that handled by the current logic?" *(Inquires about specific scenario)*

### Scenario: Minor stylistic or naming issue (Nitpick).

*   **Goal:** Suggest a small improvement without making it sound like a major issue.
*   **Avoid This Phrasing:** "Fix this naming." (Blunt, demanding)
*   **Try These Phrasings:**
    *   "Nit: Could we rename `temp` to something more descriptive like `user_profile_data` for better clarity?" *(Labels as minor, softer phrasing, specific suggestion)*
    *   "Small suggestion: Maybe align these parameters vertically for readability?" *(Clearly optional)*

### Scenario: Tests seem missing or insufficient.

*   **Goal:** Inquire about test coverage or request specific test cases.
*   **Avoid This Phrasing:** "Needs tests." (Vague)
*   **Try These Phrasings:**
    *   "Could you add a test case covering the scenario where the input list is empty?" *(Specific request)*
    *   "How is this logic tested? I couldn't find a specific test case for the error handling path." *(Asks about coverage)*

### Scenario: Potential performance issue.

*   **Goal:** Raise performance concerns constructively and inquire about benchmarks or alternatives.
*   **Avoid This Phrasing:** "This is slow." (Assertion without evidence, potentially inaccurate)
*   **Try These Phrasings:**
    *   "I'm slightly concerned about the performance here, especially if this list gets large. Have you benchmarked this or considered an alternative like [suggestion]?" *(Expresses concern, asks for data/alternatives)*
    *   "Is there a potential performance implication if this function is called frequently in a loop?" *(Asks about usage context)*

### Scenario: You don't understand the reason for a change or approach.

*   **Goal:** Politely ask for context or explanation.
*   **Avoid This Phrasing:** "Why?" (On a line of code - Abrupt, can sound challenging)
*   **Try These Phrasings:**
    *   "Could you add a quick comment explaining the reasoning behind choosing this approach?" *(Asks for context politely)*
    *   "What was the motivation for this change? Understanding the background might help me review it better." *(Explains *why* you're asking)*

---

## Part 2: Replying Constructively (Responding to Comments)

Receiving feedback can be tough, but responding professionally and openly is key to a productive review cycle. Assume good intent from the reviewer. Avoid replies that are defensive, dismissive, or uncooperative.

**Note on Replying:** While these templates often start with polite acknowledgements (like "Thanks" or "Good point"), remember to vary your replies in a real review. Using `[]` below indicates optional phrases. Sometimes a simple "Done." or "Fixed." suffices for minor points, and repeating the same phrase for every comment can sound unnatural. Adapt these templates to the specific context and your conversation with the reviewer.

### Scenario: Comment suggests your code is "hacky" or hard to understand.

*   **Reviewer Comment:** "I'm having trouble following the logic in this section. Could we perhaps simplify it or add a comment explaining the approach?"
*   **Avoid This Reply:** "It's not hacky, it works fine." or "It's obvious if you just read it carefully." (Dismissive, defensive)
*   **Try These Replies:**
    *   "[Thanks for the feedback.] You're right, it's a bit dense. I've added comments to explain the steps. Let me know if it's clearer now."
    *   "[Good point.] I've refactored this section for better readability. Updated."
    *   (If you disagree on the need for change): "[Thanks for looking closely.] I chose this approach due to [specific reason, e.g., performance needs]. I've added comments explaining the trade-offs. Does that help clarify why it's implemented this way?"

### Scenario: Comment asks about abstracting logic.

*   **Reviewer Comment:** "This logic looks potentially reusable. Do you think it makes sense to abstract it now?"
*   **Avoid This Reply:** "No." or "It's fine like this." (Uncooperative, lacks reasoning)
*   **Try These Replies:**
    *   "[Good suggestion.] I've extracted it into `new_helper_function()`. Fixed."
    *   "[Makes sense.] Abstracted this into `new_helper_function()`."
    *   "I considered that, but since it's only used here, I worried an abstraction might be overkill right now (YAGNI). Happy to abstract it if you feel strongly, though."

### Scenario: Comment points out confusion.

*   **Reviewer Comment:** "Could you walk me through this section? I'm not sure I grasp the flow."
*   **Avoid This Reply:** "It's simple, just read the code." or "Works on my machine." (Dismissive, unhelpful)
*   **Try These Replies:**
    *   "[Sure thing.] [Provide a brief explanation in the comment thread]. I've also added some inline comments to make the flow clearer in the code itself. Updated."
    *   "[Ah, right.] I've renamed a few variables (`foo` -> `user_input_buffer`, etc.) to hopefully make the intent clearer. Fixed."

### Scenario: Comment suggests an alternative approach/algorithm.

*   **Reviewer Comment:** "Have you considered Algorithm X here? What were the reasons for choosing the current algorithm?"
*   **Avoid This Reply:** "This way is better." or "Algorithm X is bad." (Doesn't engage with the suggestion, lacks justification)
*   **Try These Replies:**
    *   "[That's a great point / Good suggestion.] I looked into Algorithm X, and you're right, it seems like a better fit here. I'll make the change. Updated."
    *   "[Thanks for the suggestion.] I did evaluate Algorithm X initially, but went with the current one because [provide concise reasoning...]. Let me know if you think that reasoning is sound."

### Scenario: Comment asks about handling a specific case (e.g., null input).

*   **Reviewer Comment:** "What's the expected behavior if `input` is null here? Should we add a check?"
*   **Avoid This Reply:** "That won't happen." or "It should be obvious." (Dismissive, potentially incorrect)
*   **Try These Replies:**
    *   "[Good catch!] That was an oversight. I've added a null check and a test case for it. Fixed."
    *   "[Ah, right.] Added a check for the null case. [Thanks!]"
    *   "[Thanks for asking.] In this flow, `input` is guaranteed by the caller contract [or point to upstream validation] not to be null. Should I add an assertion `assert input is not None` to make this explicit?"

### Scenario: Comment suggests a minor stylistic change (nitpick).

*   **Reviewer Comment:** "Nit: Could we rename `temp` to something more descriptive?"
*   **Avoid This Reply:** "Who cares?" or "This name is fine." (Dismissive of small improvements)
*   **Try These Replies:**
    *   "Done. Renamed to `user_profile_data`."
    *   "[Good suggestion.] Renamed. Fixed."
    *   (If disagreeing politely): "Hmm, `temp` is used consistently in this module for this type of variable. I kept it for consistency, but happy to change if you feel strongly."

### Scenario: Comment asks for tests.

*   **Reviewer Comment:** "Could you add a test case covering the scenario where the input list is empty?"
*   **Avoid This Reply:** "It doesn't need a test." or "Testing is a waste of time for this." (Undermines quality)
*   **Try These Replies:**
    *   "[Good point.] I've added a test for the empty list scenario. Updated."
    *   "[Makes sense.] Added a test case in `test_module.py::test_empty_input`. Fixed."
    *   (If tests exist elsewhere): "This scenario is actually covered by the integration test in `test_integration.py` which sends an empty list. Should I add a specific unit test here as well for clarity?"

### Scenario: Comment raises performance concerns.

*   **Reviewer Comment:** "I'm slightly concerned about the performance here if the list gets large. Have you benchmarked this?"
*   **Avoid This Reply:** "It's fast enough." or "Don't worry about it." (Dismissive, lacks evidence)
*   **Try These Replies:**
    *   "[Thanks for raising that.] I ran a quick benchmark for N=10,000 and it completed in X ms, which seems acceptable for our expected scale. Let me know if you foresee larger inputs."
    *   "[You're right,] performance could be an issue at scale. I've switched to using [alternative approach] which should be more efficient. Updated and added a benchmark test."
    *   "[Good point.] I haven't benchmarked it formally, but based on [reasoning...], I didn't anticipate issues. I can add a benchmark if needed."

### Scenario: Comment asks "Why?" or requests reasoning.

*   **Reviewer Comment:** "Could you add a comment explaining the reasoning here?" or "Why this approach?"
*   **Avoid This Reply:** "Because." or "It's legacy code." (Unhelpful, avoids explanation)
*   **Try These Replies:**
    *   "[Good question.] I chose this approach because [explain reason briefly...]. I've added a comment to the code to clarify this. Updated."
    *   "[Makes sense to clarify.] Updated the code comments to explain the rationale here."