# Who Is Reviewing Your Design Doc? You Think It's About Technology, But It's Actually About Motivation

## The Exam Student Syndrome

Ever submitted what you thought was a brilliant design document only to watch it get torn apart in review? I've been there. 

We engineers often write design docs like we're taking an exam, desperately searching for the "correct" technical answer. But here's the truth: nobody is grading your design on technical perfection alone.

At Spotify, an engineer created what they thought was a masterpiece service mesh design. The architecture looked great, the performance numbers were solid. But it got shot down because nobody actually thought about how people would *use* it. Technical brilliance: 10/10. Real-world awareness: 2/10. [1]

## It's Not About Your Solution, It's About Their Problems

Think about the last time you got pushback on a design. Was it really about your technical approach? Or was it about how your design affected the people reviewing it?

When Amazon's DynamoDB team started with a rigid consistency model, they faced resistance from teams with different needs. Their breakthrough wasn't a better algorithm—it was giving teams a "consistency knob" so everyone could make their own trade-offs. "You decide how paranoid you want to be!" suddenly made everyone happy. [2]

## Know Your Reviewers (Before You Write a Single Line of Code)

Let's get real about who's actually reviewing your design and what they actually care about:

### The Tech Lead 
> "AKA The Guardian of 3AM Incidents"

Tech Leads aren't worried about today. They're having nightmares about maintenance six months from now when you're vacationing on a beach somewhere.

A brilliant payment system redesign got rejected until the author added a "Dear Future Maintainer: Here's How This Crazy Thing Works" guide. Tech Leads love rollback strategies like skydivers love backup parachutes—for exactly the same reason. [3]

**Pro tip:** Don't just explain what your system does. Explain how someone who isn't you would debug it at 3AM.

### The Platform Engineer 
> "AKA I Built This Platform and You're Ignoring It?!"

Nothing makes platform teams sadder than hearing their baby is ugly. They've spent years building standardized systems to prevent fragmentation and ensure maintainability! Ignoring this investment often raises legitimate concerns about duplicated effort and long-term support.

When engineers needed something faster than the standard data pipeline, they were smart enough not to say "your system sucks." Instead, they called their solution a "specialized extension" and offered improvements to the standard platform too. [4]

**Pro tip:** Position yourself as enhancing the platform, not replacing it. Highlight how you integrate with or improve the existing ecosystem.

### Your Peers 
> "AKA The Commentary Spectrum"

Let's be honest: some review comments exist solely to show how smart the reviewer is.

Ever had someone suggest rewriting your MongoDB service in PostgreSQL without addressing why you chose a document database in the first place? It's like suggesting a submarine when you need a helicopter. Thanks, but no.

One team dealt with this brilliantly by creating a "criticism priority matrix" to sort feedback from "will literally catch fire in production" to "just their personal coding style preference." [5]

**Pro tip:** Acknowledge all feedback, but prioritize comments that solve actual problems over those that just sound smart.

### The Business-Minded Engineer 
> "AKA The 'Ship It' Squad"

These folks will happily take out technical debt loans if it means beating competitors to market. In high-velocity markets, this isn't just impatience; it's often a calculated trade-off, prioritizing speed and learning over initial perfection.

A social network's first friend recommendation algorithm was so simple it made engineers cry—but it boosted connections by 40%. [6] Another company initially stored payment data without proper persistence. Was it technically perfect? Nope. Did it let them launch months earlier? Absolutely.

**Pro tip:** Always connect your technical decisions to business outcomes. Nobody funds architecture for architecture's sake.


## How to Get Your Design Approved (Without Sacrificing Your Vision)

**Do your homework on reviewers.** Study their past comments and concerns. One team found they got approvals 60% faster by creating a pre-emptive checklist of each reviewer's typical concerns.

**Customize your pitch.** Break up your document into sections that speak to different audiences—reliability metrics for operations folks, cost breakdowns for finance people, performance benchmarks for platform teams.

**Have the hard conversations in private.** Hold short preview discussions with key reviewers before formal meetings. These 15-minute chats are crucial for de-risking the formal review; they surface blockers early, allow for refinement, and build consensus, turning potential battlefield debates into smooth formalities, especially in organizations with complex dependencies.

**Make everyone feel like a co-creator.** One successful API redesign explicitly credited ideas from various teams and incorporated their terminology. Everyone loves seeing their name in lights! [7]

## The Hard Truth About Design Documents

Great design docs aren't technical masterpieces—they're interpersonal achievements.

The best chaos engineering practices succeeded because authors evolved their proposal from "our cool tool" to "our company's approach." [8] 

The best design outcomes make everyone feel like participants, not spectators. When everyone feels ownership, resistance transforms into advocacy.

Remember: in design reviews, it's not about having the perfect technical solution. It's about understanding what motivates the humans who'll be reviewing it. 

And let's be honest, most design documents aren't proposing revolutionary technical breakthroughs. They're about applying existing tools to solve business problems – solutions often implemented elsewhere years ago. It's frequently about skillfully adapting proven patterns to a specific context, not just reinventing wheels. The required level of detail hinges on company size and culture; a sprawling enterprise needs more than a nimble startup focused on a proof-of-concept. Ultimately, the goal isn't technical novelty, but building consensus and adapting solutions to your unique needs.

## References

[1] Spotify Engineering Culture Blog, "Why Technical Documentation Matters," 2019
[2] DeCandia et al., "Dynamo: Amazon's Highly Available Key-value Store," SOSP '07
[3] Larson, W., "Staff Engineer: Leadership Beyond the Management Track," 2021
[4] Airbnb Tech Blog, "Real-time at Airbnb," 2018
[5] Twitter Engineering Blog, "Timeline Ranking," 2017
[6] Facebook Engineering Blog, "People You May Know," 2016
[7] Salesforce Engineering Blog, "API Design at Scale," 2020
[8] Basiri et al., "Chaos Engineering," IEEE Software, 2016
