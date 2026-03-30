# SmartTranscripts

## Details
- URL: https://github.com/tevslin/smarttranscripts
- Highlight: A free, open-source framework for converting public meeting video into interactive, searchable, and shareable web pages.
- Summary: SmartTranscripts is open-source software that turns video recordings of public meetings into interactive transcripts with searchable text, speaker identification, and synced video playback. Active deployments exist in Vermont, New York State, San Francisco, and Connecticut.

## What is this for?
SmartTranscripts takes public meeting recordings and produces interactive web pages that can be used to quickly scan and discover key moments within each proceeding. Every meeting transcript is synced to its source video, so users can highlight text, click play, and jump to that exact moment in the video. The pages also include full text search and a searchable agenda.

The software is open-source and must be deployed and operated independently by local organizations or individuals. Each deployment is customized to its local environment, including how meetings are discovered and how committee member lists are populated.

Active examples include:
- Golden Dome VT ([goldendomevt.com](https://goldendomevt.com/)) for Vermont's state legislature
- New York State SmartTranscripts ([nys.smarttranscriptsai.com](https://nys.smarttranscriptsai.com/))
- San Francisco Government Connection ([sfgovernmentconnection.com](https://sfgovernmentconnection.com/))
- Legitalk - Connecticut legislative hearings ([theconnecticutmirror.com](https://theconnecticutmirror.com/))

The project's founder, [Tom Evslin](https://en.wikipedia.org/wiki/Tom_Evslin), describes himself as "a provider of technology and tools" who does not operate the individual instances. This means that each deployment requires a local organization with the technical capacity to run and maintain the software. Evslin has stated he could get a new instance running in a day or two, but organizations that require internal approvals at each step may take longer, and Evslin is not in the business of maintaining each instance.

## How is AI used?
SmartTranscripts uses a multi-step AI pipeline for meeting transcription and speaker identification. [Deepgram](https://deepgram.com/) handles the initial transcription and diarization, which Evslin reports is approximately 95% accurate at distinguishing between speakers. This makes it a good option for its intended application: covering state government. It also has a thoughtful design to ensure that known speakers are spelled and identified correctly.

The transcript is then passed to ChatGPT, which attempts to match speakers to known names and roles, and returns a confidence score for a speaker’s identity. If the result returns a > 90% accuracy speaker identification score, the system is designed to assign the known identity. When it is not confident, it does not assign one. There is no manual override for speaker identification; the process is currently fully automated.

## What makes it different from other tools?
SmartTranscripts is free and open-source, which sets it apart from nearly every other tool in this space. It is designed to be operated by local organizations rather than centrally hosted, giving each deployment control over its own data and coverage. And because it's open-source, any organization or individual can customize it or submit their own features for review.

CTMirror's build of Legitalk is one example of this in practice. AI data reporter Angela Eichhorst used the tool's documentation and open architecture to customize it for her newsroom's specific coverage needs. "Because of [SmartTranscripts'] clear documentation, and available AI coding agents, I have managed to add reporters' requests," says Eichhorst. "For example, I changed the AI API prompt to add a summary item each time a bill is mentioned — an idiosyncrasy of CT government is that speakers discuss bills at multiple times throughout meetings out of order."

The software also takes a deliberate approach to video hosting. It does not repost or rehost meeting videos, instead it links back to the original source and uses embeds from the original provider. This purposeful choice was made to avoid terms of service violations, keep hosting costs low, and drive traffic back to the original, trusted source.

## Pros
- Free and open-source, with no licensing costs for organizations that want to deploy it
- The speaker identification pipeline combines Deepgram with a ChatGPT confidence layer that attempts to avoid assigning identities when uncertain
- Built specifically for covering state government, which many other tools are currently not configured to support

## Cons
- Each deployment requires a technically capable operator to install, customize, and maintain
- Speaker identification is fully automated with no manual override, so errors cannot currently be corrected by users

## Newsroom clients
CTMirror's Legitalk, built on SmartTranscripts, launched in 2026.

## Note
The American Journalism Project does not have a formal partnership with SmartTranscripts. This snapshot is based on available public and submitted information to support independent newsroom evaluation.