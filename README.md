# Understanding-Query
## LLMSearch features:
1.	Uses an LLM to rewrite the query for better search results.
2.	Uses the google customized search API to collect urls.
3.	Filters and prioritizes urls by local whitelist/unknown/blacklist, and by past history of usefulness
4.	Uses concurrent futures to process urls in parallel.
5.	Preprocesses url returns to extract a minimal piece of candidate text to send to gpt-3.5 for final refinement

Four ways to use this:
1.	as a chatGPT plugin (if you are a plugin developer)
2.	as a network endpoint for your application
3.	as a standalone command line search tool 'python3 search_service.py'
4.	directly from within a python application: import search_service, then call search_service.from_gpt(query_string, search_level)

will need google customized search api key and your google cx.
will also need an openai api.key.

## INSTALLATION:
1.	clone the repository
2.	pip3 install -r requirements.txt
3.	add your openai.api_key either as an evironment var or directly in utilityV2.py
4.	add your google credentials either as environment vars or directly in google_search_concurrent.py
to test, try: python3 search_service.py
you should see:
Yes?
To run: python3 main.py
The endpoint returns json with source, url, response, and credibility keys.
