WSJ Financial News – XML & DTD Project
Overview

This project models Wall Street Journal (WSJ) financial news articles using XML and a custom DTD. The goal is to capture the essential structure of an article — including metadata like publish time, company ticker, stock market data, and sentiment — and validate it with both correct and incorrect XML examples.

A Colab notebook (validate.ipynb) is included to demonstrate validation of the XML files against the DTD.

Framework

Decision: Which WSJ financial articles should be prioritized for quick investment insights?

Signals:

title — headline of the article [News]

summary — concise recap [News]

category — type (Finance, Economy, Markets) [News]

publishTime — ISO timestamp, freshness of report [News]

company — name & ticker [Markets]

marketData — stock price and % change [Markets]

source — WSJ credibility label [News]

sentiment — positive, neutral, or negative tone (Analytics)

Gaps: Missing bond yield data [Markets] would improve confidence when interpreting market reactions.

Risk: A mismatch between [News] reporting and [Markets] data may cause misleading interpretations, especially if articles emphasize sensationalism over fundamentals.

Stewardship: WSJ financial articles should remain subscription-only. Market data should be retained for no more than 90 days for analysis, and redistribution outside licensed use is prohibited.

Data Domain:

Primary: [News/WSJ]

Adjacent: [Markets], [Economy]

Citation: Written by me; AI (ChatGPT) was used to refine wording and XML formatting.

Files

domain.dtd → Defines the structure of a WSJ article.

sample.xml → Valid XML example that passes DTD validation.

broken.xml → Invalid XML example that fails validation (missing <summary>).

validate.ipynb → Colab notebook showing validation results.

Broken XML Explanation

The broken.xml file fails validation because the <summary> element is missing, violating the required order defined in domain.dtd.
