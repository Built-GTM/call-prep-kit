# Every word in this kit, in plain English

Nothing here needs a technical background. If a word in the walkthrough confused you, it is defined below.

## The things you are building

**Agent** &middot; An assistant you set up once and then talk to. It remembers its job between conversations. Think of a new hire with one task rather than a chatbot.

**Bot** &middot; What this platform calls an agent. Same thing.

**The build block** &middot; One long piece of text that contains the whole agent: who it is, what it does, what it must never do, and the shape of what it hands you. You paste it in once. That is the build.

**The binder** &middot; The folder of short text files about *your* business: what you sell, who fits, who signs, who you already serve. **The agent reads it and never changes it.** This is the part that makes the agent yours instead of generic, and it is the part we do not ship, because someone else's binder would make your agent confidently wrong.

**The card** &middot; What the agent hands you before a meeting. One per meeting, same shape every time, readable in about twenty seconds.

## Where things live

**`/workspace/...`** &middot; A folder on the agent's own computer in the cloud. **It is not your laptop.** The agent cannot see your machine. The slashes just mean folders, the same way they do anywhere else. You never create these by hand and you never browse to them: you ask the agent and it tells you.

**Connector** &middot; Permission for the agent to look at one of your other accounts, like your calendar. You sign in once and it remembers.

**Read access** &middot; It can look. **Write access** &middot; It can change or send things. For this agent, read is all you want.

**Sync** &middot; Copying your binder from your drive onto the agent's computer. You do it once at setup and again whenever you change something.

## The ideas that matter

**Waterfall** &middot; Trying the cheapest way to find something first, and only paying for a more expensive way if the cheap one comes back empty.

**Enrichment** &middot; Looking someone up from their email address to find their job title, how long they have been there, and where they worked before.

**Context** &middot; Everything the agent knows about your business. Your binder is your context.

**Prompt** &middot; The instructions you give it. In this kit the build block *is* the prompt.

**Hallucination** &middot; When an agent states something untrue in exactly the same confident tone it uses for things that are true. This is why the rules in the block are so blunt about sources, and why you test it before trusting it.

**Drift** &middot; When your binder quietly changes and every answer after it is wrong without anything looking broken. The reason the agent is forbidden from editing the binder at all.

## Words you will meet elsewhere and can ignore here

| You will see | It means | In this kit |
|---|---|---|
| context pack, knowledge base, RAG | files the agent reads | **the binder** |
| system prompt, instructions | who the agent is | **the build block** |
| tool, function, integration | something it can reach | **a connector** |
| eval, test harness | checking it before you trust it | **the test meetings** |
| schema, output contract | the fixed shape of the answer | **the card** |
