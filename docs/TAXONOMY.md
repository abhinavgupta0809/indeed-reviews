# Taxonomy v1 (Indeed Job Search)

Written by Claude after reading a stratified sample of about 230 reviews from the Oct 10, 2026
scrape (46,454 reviews in 90 days, sampled to 20,000). Machine-readable copy:
`analysis/taxonomy.json`. The prompt the model sees: `docs/annotation_prompt.md`. If these three
disagree, `taxonomy.json` wins for validation and this file gets fixed.

## Labels: what kind of review is it

Same six as the Perplexity run. One or two per review. The first is the primary label.

| Label | Use when | Categories |
|---|---|---|
| Specific Praise | Positive, and names a feature, a quality, or an outcome | 1-2 |
| Specific Complaint | Negative, and names a concrete problem | 1-2 |
| Feature Request | Asks for something to be added, changed, or brought back | 1-2 |
| Generic Good | Positive with nothing specific ("great app", "very helpful") | none |
| Generic Bad | Negative with nothing specific ("worst app", "useless") | none |
| Nonsense | Unintelligible, off-topic, wrong app, abuse with no product content, **or a job plea** | none |

Rules:

- **Specific outranks generic.** "Good app but full of fake jobs" is `Specific Complaint, Generic Good`.
- **Two specific labels:** order by which takes more of the text. Tie goes to the complaint.
- **Never pair** Generic Good with Specific Praise, Generic Bad with Specific Complaint, or Generic
  Good with Generic Bad. Nonsense always stands alone.
- **Job pleas are Nonsense.** Indeed's review box collects text that isn't a review: a work history
  ("I have 39 years of experience in housekeeping"), a request ("I need a job please"), a message
  to an employer ("I would very much like to work for your company"). It says nothing about the
  app. If the same review also says something about Indeed, label that part and ignore the plea.
- **"Easy to use" is specific** (UI / UX). "Helpful", "good for finding jobs", "best job app" with
  nothing else are Generic Good.
- **A bare comparison is not specific.** "LinkedIn is better" is Generic Bad with a competitor tag.

## Categories: what part of the experience

Up to two, most important first. Empty for Generic Good, Generic Bad, and Nonsense.

The first five are about the job market Indeed hosts. The rest are about the product. Keeping them
apart matters: Indeed controls the second group fully and the first only partly.

| Group | Category | Covers |
|---|---|---|
| Marketplace | Employer Response & Status | Applying and hearing nothing; no call, no rejection, no feedback; not knowing an application's status; praise for employers replying quickly |
| Marketplace | Job Outcomes | Got a job or interviews through Indeed; or used it a long time and never got one, with no cause named |
| Marketplace | Fake & Scam Listings | Scams, fake or ghost jobs, listings that charge fees, employers who aren't hiring, expired jobs still shown; praise for jobs being real |
| Marketplace | Listing Details & Quality | Missing or wrong information in a listing (pay, address, posting date, requirements), one company flooding results, sponsored jobs pushed to the front, low-quality or underpaid offers |
| Marketplace | Job Availability | Many jobs, wide variety, jobs in my field or country; or few or none |
| Finding | Search & Filters | Keyword search ignoring terms, filters broken, hidden, or removed, job type and remote filters, sorting, hiding jobs or companies |
| Finding | Location & Distance | Radius, commute time, or city not respected; jobs hours away; no walking-distance option |
| Finding | Recommendations & Relevance | The feed or suggested jobs don't fit the profile or preferences; the same jobs repeating; praise for good matches |
| Applying | Applying | The apply flow: quick apply, too many steps, screener questions, being sent to company sites, the daily apply limit |
| Applying | Resume & Profile | Resume builder and upload, formatting, AI rewriting a resume, profile fields, education and experience options |
| Applying | Messages & Interviews | Messaging employers, interview scheduling, messages not showing, contact details for employers |
| Applying | Notifications & Emails | Too many emails or alerts, irrelevant alerts, timing, prompts to follow up; praise for timely alerts |
| Applying | AI Features | The AI assistant, AI search, AI screening of applications, AI messages; "AI ruined it" |
| App | Login & Account | Sign-in, verification codes, the phone-number requirement, account recovery, changing a number, signup questions, age rules |
| App | Privacy & Data | Data being sold or shared, spam calls and texts after applying, personal information requested |
| App | Customer Support | Help center not reachable or not resolving; no phone line for job seekers |
| App | Bugs & Performance | Crashes, freezes, blank screens, "can't find this page", features that stopped working, slow or fast |
| App | UI / UX | Ease of use, layout, navigation, redesigns, dark mode |
| App | App vs Website | Being pushed from the website into the app, features that differ between the two |
| | Other | Specific, but fits nothing above (company reviews, language support, ads, and so on) |

Tie-breakers the sample forced:

- **No response vs no job.** Mentions applying and not hearing back, being ignored, or not knowing
  the status: Employer Response & Status. "Never got a job here" or "found my job here" with no
  mention of responses: Job Outcomes.
- **Praise for replies vs praise for results.** Employers reply, call, or message quickly: Employer
  Response & Status. Landed a job or interviews: Job Outcomes.
- **Fake vs ghost vs silence.** Says the jobs are fake, scams, or not really hiring: Fake & Scam
  Listings. Says only that nobody replied: Employer Response & Status. Both said: fake first.
- **Search vs recommendations.** Results of a search they typed or filters they set: Search &
  Filters. What the app shows, suggests, or emails unprompted: Recommendations & Relevance.
- **Distance.** Anything about miles, km, radius, commute, or the wrong city: Location & Distance
  first, even when filters are named.
- **AI.** Use AI Features when the reviewer blames or praises AI by name. Pair it with the part it
  touched (Search & Filters, Applying, Resume & Profile) when one is named.
- **Spam.** Calls or texts from strangers after applying: Privacy & Data. Too many emails from
  Indeed: Notifications & Emails.
- **Broken vs badly designed.** Doesn't work: Bugs & Performance. Works but is awkward: UI / UX.
- **Easy.** "Easy to use" is UI / UX. "Easy to apply" is Applying. "Easy to find jobs" is Job Availability.

## Other fields from the model

Unchanged from the Perplexity run, so the pipeline needs no code change.

| Field | Rule |
|---|---|
| `sentiment_rating` | 1-5 from the text alone, ignoring the stars. Nonsense gets 3. |
| `language` | ISO 639-1 code of the text as written. Romanized Hindi is `hi`. Undeterminable is `und`. |
| `english_translation` | Faithful translation when the language isn't English. Empty otherwise. |
| `topic` | 2-6 lowercase English words naming the specific thing ("no reply after applying"). Empty for generic and nonsense. |
| `competitors` | Products named, from the fixed list: LinkedIn, ZipRecruiter, Glassdoor, Naukri, SEEK, Apna, Monster, Google, Other. |
| `regression_claim` | True when the reviewer says Indeed got worse than it used to be. |

Computed columns (`rating_mismatch`, `is_low_signal`, `is_duplicate_text`, `is_truncated`,
`needs_translation`) are unchanged.

## What the sample showed

Read before anything is labeled, so treat these as expectations to test, not findings:

- The sharpest complaints are about the marketplace: applying many times and hearing nothing, and
  fake, scam, or ghost listings.
- Search is the main product complaint: filters removed or hidden, distance not respected, results
  that ignore the terms. Several reviewers tie this to a recent update and to AI.
- iOS is a different population: 2.29 average stars against 4.50 on Android, and only 17% of iOS
  reviews are under four words against 55% on Android.
- Many 5-star Android reviews are job pleas or bare praise, so the star average says little.
- Rough keyword counts on English reviews of eight or more words: scam or fake 331, search and
  filters 285, distance 225, login and account 185, pushed into the app 184, no response 154.
