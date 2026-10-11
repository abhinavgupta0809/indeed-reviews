# Phase 02 gold-set evaluation

Gold rows: 117

Rows with annotation_error: 0

## Agreement

| Metric | Matches | Rows | Value | Target | Status |
| --- | --- | --- | --- | --- | --- |
| Primary label accuracy | 110 | 117 | 94.02% | 85.00% | PASS |
| Label set overlap | 112 | 117 | 95.73% | — | — |
| Primary category agreement | 73 | 80 | 91.25% | 80.00% | PASS |
| Low-signal agreement | 36 | 37 | 97.30% | — | — |
| Sentiment within one point | 117 | 117 | 100.00% | — | — |

Sentiment mean absolute error: 0.2821 over 117 scored rows. Missing/failed sentiment rows: 0. Within-one-point accuracy uses every gold row; missing/failed results count as misses. Failed annotations also count as misses on label/category/low-signal metrics.

## Primary-label confusion matrix

| Gold primary label | Specific Praise | Specific Complaint | Feature Request | Generic Good | Generic Bad | Nonsense | (missing) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Specific Praise | 29 | 0 | 0 | 1 | 0 | 1 | 0 |
| Specific Complaint | 0 | 44 | 0 | 0 | 0 | 1 | 0 |
| Feature Request | 0 | 2 | 1 | 1 | 0 | 0 | 0 |
| Generic Good | 1 | 0 | 0 | 31 | 0 | 0 | 0 |
| Generic Bad | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| Nonsense | 0 | 0 | 0 | 0 | 0 | 4 | 0 |

## Per-category agreement

Gold count includes each row whose gold category set contains that category. A match requires the model's primary category to equal that category; a two-category gold row can appear in two denominators.

| Category | Gold count | Primary-category matches | Agreement |
| --- | --- | --- | --- |
| Employer Response &amp; Status | 14 | 11 | 78.57% |
| Job Outcomes | 19 | 16 | 84.21% |
| Fake &amp; Scam Listings | 12 | 11 | 91.67% |
| Listing Details &amp; Quality | 5 | 3 | 60.00% |
| Job Availability | 8 | 3 | 37.50% |
| Search &amp; Filters | 10 | 4 | 40.00% |
| Location &amp; Distance | 4 | 3 | 75.00% |
| Recommendations &amp; Relevance | 5 | 4 | 80.00% |
| Applying | 6 | 4 | 66.67% |
| Resume &amp; Profile | 0 | 0 | n/a |
| Messages &amp; Interviews | 0 | 0 | n/a |
| Notifications &amp; Emails | 5 | 0 | 0.00% |
| AI Features | 3 | 2 | 66.67% |
| Login &amp; Account | 3 | 2 | 66.67% |
| Privacy &amp; Data | 1 | 0 | 0.00% |
| Customer Support | 1 | 1 | 100.00% |
| Bugs &amp; Performance | 9 | 6 | 66.67% |
| UI / UX | 6 | 3 | 50.00% |
| App vs Website | 0 | 0 | n/a |
| Other | 1 | 0 | 0.00% |

## All label/category/low-signal disagreements (10)

Every disagreement on primary label, primary category, or low-signal agreement is included once. Text is sliced to 300 Unicode characters before Markdown escaping; no row limit is applied.

| Review ID | Stars | Review text (first 300 characters) | Gold labels | Gold categories | Model labels | Model categories | Model topic |
| --- | --- | --- | --- | --- | --- | --- | --- |
| play_9e946bbe-7089-4e44-9c30-776e35a186ad | 1 | Doesn't save my preferences, which in turn don't show me the jobs I'd be looking for in my area or pay range. | Specific Complaint | Search &amp; Filters \| Location &amp; Distance | Specific Complaint | Recommendations &amp; Relevance, Location &amp; Distance | preferences not saved |
| play_f1d6fa1b-73ef-44c4-9a05-3853b6595e0d | 2 | need more consequences for employers posting fake jobs or using inadequate automation tools for filtering applications | Feature Request | Fake &amp; Scam Listings \| AI Features | Specific Complaint | Fake &amp; Scam Listings, Applying | fake jobs and weak application filtering |
| play_4ae41d12-14c4-4b75-992b-5fa81e8d803a | 2 | it's would be great if it actually showed what the jobs paid. I've gone on multiple interviews for places that don't post salary or pay rate only to find out they underpay the position. wingstop offered a management position for $14/hr when I was at a job that paid $18/hr for the same position. all  | Feature Request | Listing Details &amp; Quality | Specific Complaint, Feature Request | Listing Details &amp; Quality | salary missing from listings |
| play_ee045b49-b374-4f36-9777-8b27e7011d30 | 3 | very nice ksi dimuna kilangan pan mag lakad mag hihitay kana lang tawag🤍 | Specific Praise | Applying | Nonsense |  |  |
| play_2984b4bf-1ece-42e9-b08f-31c7f98eac39 | 4 | it alway find the best job to fit what I am searching for ,and it easy to understand | Specific Praise | Search &amp; Filters \| UI / UX | Specific Praise | Recommendations &amp; Relevance, UI / UX | good job matches |
| play_08911226-88a0-4257-b6f4-b7de0f79893b | 4 | Much improved from earlier versions, this free app is perhaps the best resource and easiest to use to help candidates locate new opportunities, identify roles, track applications, and even practice interviewing. | Specific Praise | UI / UX \| Job Availability | Specific Praise | Applying, Messages &amp; Interviews | tracks applications, interview practice |
| play_02db0d07-9e8f-4296-8657-50213765cfb4 | 5 | Hello, indeed. I did try to use your site, it Was amazing, i just a simpler version. ok bye | Feature Request \| Generic Good | UI / UX | Generic Good |  |  |
| play_52c6b329-2d09-4575-b544-fd23db9658b7 | 4 | cuando me den Chamba suben a 5 estrellas | Specific Complaint | Job Outcomes | Nonsense |  |  |
| play_5268f3e9-d1bb-4d47-b23e-74376477a7a2 | 5 | es muy buena encuentro buenas opciones | Generic Good |  | Specific Praise | Job Availability | good job options |
| play_de9cac67-0ed2-4e3f-93bd-17920e668d80 | 5 | Ótima opção para quem está precisando de uma vaga de trabalho. Rápido e preciso! | Specific Praise | Bugs &amp; Performance | Generic Good |  |  |
