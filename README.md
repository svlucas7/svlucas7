# Lucas Silva

Analytics engineering and product.

I work where a business rule meets a dataset. The rule is usually what decides whether the query is right, and it is usually written down nowhere near the data. Most of the mistakes I have shipped were not SQL mistakes. They were me being confident about a rule I had not checked.

Software engineering student at PUC Minas. I work at OKTZ as a growth technology analyst, where I own the tracking, the dashboards and the automation around them: GA4 and GTM through to BigQuery, Power BI and Looker Studio on top, and the Python and n8n automation that connects paid media to the Sankhya ERP.

## What I am working on

**[procurement-integrity-warehouse](https://github.com/svlucas7/procurement-integrity-warehouse)** is about a rule that moves every year and an exception that most people miss.

Governments let public bodies buy small things without running a tender. There is a value ceiling, and this finds contracts above it. Two things make that harder than a `where` clause. The ceiling is re-indexed to inflation every January, so it is a slowly changing dimension, and hardcoding today's number quietly misjudges every older record while still returning rows. And most contracts awarded this way have no ceiling at all, so a detector that does not know which ones would announce a lawful R$ 119 million emergency purchase as fraud, by name, in public.

One day of real data: 2,564 notices, 14 flagged, 224 correctly left alone. The most useful thing in the repo is the test that catches me. My first version was circular, because it read the rule from the same file the model reads, and I only found out by sabotaging the file and watching the test cheerfully agree with the error.

Public procurement is the case study, not the point. The same shape shows up anywhere a regulator sets a number and then moves it.

Python, dbt, DuckDB, BigQuery, Dagster.

**Biddexia** is a tender intelligence product I built and run for the UK market. It is live, and I wrote all of it.

The part worth talking about is the ingestion. Four public sources, each with its own schema and its own opinions about being read, running daily with per-source failure isolation so one publisher changing a field cannot take the run down with it. Around 33,000 notices. Behind that: the Postgres schema, entity normalisation so a buyer's history matches across spelling variants of the same supplier, scoring on Azure OpenAI with structured outputs and a fallback chain for when a provider rate limits, Stripe, and the event taxonomy and funnel instrumentation in PostHog.

The code is private because it is commercial. The analytics work in the warehouse above is the same shape, and that one you can read.

Most of my commit history here is private and it is mostly this. Around 3,000 contributions a year into something that runs rather than into a public repo.

## What I actually do

At work: BigQuery, Power BI, Looker Studio, GA4, GTM, PostHog, and the Python, Apps Script and n8n automation that keeps paid media, the site and the Sankhya ERP telling the same story. Excel too, more than I expected, because it is still where a lot of decisions actually get made.

In my own projects: SQL and dbt, dimensional modelling, data quality tests that fail for the right reasons, Postgres, DuckDB, and Python for ingestion against APIs that do not want to be ingested.

Before any of this I spent two years as a public procurement analyst, reading tender documents for a living. That is where I learned that the interesting part is never the query. It is working out what the number is supposed to mean, and what would have to be true for it to be wrong.

## Reaching me

[LinkedIn](https://www.linkedin.com/in/silvalucasdev7/) or lucashrs1108@gmail.com
