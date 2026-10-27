BYU 2026–2027 undergraduate course descriptions

Main deliverable: byu_2026_2027_course_descriptions.csv
Review subset: courses_needing_review.csv
Candidate evidence: catalog_match_candidates.csv
Counts: retrieval_summary.json

Every input row, original column, and original row order is preserved. original_row_number is 1-based and excludes the header. No sustainability classification was performed. This deliverable supersedes the earlier INTERIM CSV.

Source and method
Access succeeded after the environment Internet setting changed. BYU robots.txt allows public access. The catalog homepage identifies itself as the 2026–2027 Undergraduate Catalog. Inspection of its public JavaScript revealed the unauthenticated JSON API actually used by the catalog:
https://app.coursedog.com/api/v1/cm/byu/courses/search/%24filters
Catalog ID: SDA0rZZwClSdh47nMnGv
Catalog effective date range: 2026-09-02,2026-09-02 (taken from the website settings).
Applied the website's own active-course and course-number-under-600 filters, without broadening to other catalog years. Retrieved 5,936 records in six sequential batches of at most 1,000 with a one-second pause between requests. No authentication or access controls were bypassed. Raw responses and exact request URLs are retained in catalog_cache/; retrieval timestamps are in the CSV and metadata JSON.
Four representative public course pages were checked against the structured responses, including a blank description and the two conflicting EXDM 418 records. This was a targeted cross-check, not page-by-page scraping.

Matching
Matched Teaching Area plus Course Number to official subjectCode plus courseNumber, then compared the input title to the official name, longName, or displayName. Unicode compatibility, whitespace and case normalization were permitted; no fuzzy-title substitution was used. Every row had at least one code/title match. The input contains no catalog identifier, so distinct official identifiers sharing the same code/title cannot be disambiguated by input row order.
All matching identifiers and course-page URLs are retained. Identifier is the official revision ID; courseGroupId is used by the public page URL. Some official code fields disagree with the subjectCode/courseNumber fields; these rows are explicitly flagged, even where another candidate has a consistent code.

Descriptions
complete_description contains the full description field, with outer whitespace trimmed and HTML markup converted to readable text without summarizing. description_raw retains the exact official field for unambiguous matches. Where multiple matching identifiers have identical text, that text is supplied and the ambiguity is flagged. EXDM 418 has two conflicting descriptions: the main CSV leaves the description blank for its two input rows; both full alternatives appear in catalog_match_candidates.csv. A missing description means the official response's description field is empty, not that a shorter description was substituted. No descriptions were invented or borrowed from other catalog years.

Departments
The department column preserves the input Teaching Area abbreviation. official_department supplies the official department name where the matched data provides one. 180 rows have no official department listed, so official_department is blank; no department name was inferred. This optional metadata absence is not counted as a description-matching failure.

Review flags
manual_review_required covers missing descriptions, conflicting descriptions, ambiguous identifiers, duplicates and inconsistent catalog code fields. Flags overlap; use the boolean's total rather than summing category counts. The 10 duplicate input rows form five pairs and all are preserved. Multiple different titles under a shared code are separately flagged; repeatable/topic courses legitimately share codes, so this alone is not treated as a mismatch or manual-review requirement.

Validation
Verified output row count and order and exact preservation of every original field. Verified each populated complete_description against the cached matched official descriptions. The API count and collected count both equal 5,936, with 5,936 unique official revision IDs. No title-unmatched records were found.
