# BYU sustainability course screening

This is a conservative first-pass assessment of the uploaded 2026–2027 course-description CSV. It identifies explicit sustainability connections and separates uncertain records for manual review. It does not certify AASHE STARS eligibility, determine sustainability-focused versus sustainability-inclusive status, establish learning outcomes, or count unique course offerings for reporting.

## Files

- `clearly_sustainability_related.csv`: courses with clear description evidence and no unresolved catalog/duplicate flags. Each row includes the complete description, a verbatim evidence quotation, sustainability theme and classification rationale.
- `courses_for_manual_review.csv`: missing/conflicting descriptions, unresolved catalog/duplicate issues, potentially relevant but insufficient evidence, and variable/project-specific courses needing a current syllabus or instructor confirmation.
- `all_courses_screened.csv`: all 5,936 original rows and original columns, in original order, plus the assessment columns. This is the audit trail, including courses not placed in either subset.
- `assessment_summary.json`: row counts and theme counts.

## Meaning of classifications

`clear_sustainability_connection` means the official description explicitly covers a recognizable environmental or social/economic sustainability topic, challenge, solution or application. Environmental connections include climate/energy transition, conservation and restoration, natural-resource management, sustainable food systems, water/sanitation, pollution prevention and environmental health, sustainable design and reporting. Social/economic connections include poverty and development, human rights, inequality, inclusion/access barriers, health equity, humanitarian engineering and disaster resilience. A connection may be one component of a broader course; this is not a claim that the whole course focuses on sustainability.

`manual_review` means the available evidence cannot support a confident inclusion or exclusion. Missing descriptions must be obtained; catalog identifier/code conflicts and duplicates must be resolved; vague/variable courses should be checked against the current syllabus and learning outcomes. Broadly adjacent subjects are deliberately retained for review. The review list is a high-recall screening queue and contains false positives; it is not a list of additional confirmed sustainability courses.

`no_clear_evidence_in_catalog` means the provided text did not establish a sufficiently explicit connection in this screen. It does not mean the course could never include sustainability. All such rows remain in the audit file.

## Method and limits

All rows were processed. Broad text screening identified possible environmental, social, economic, equity and variable-topic connections for review. The clear list was selected through contextual reading of candidate descriptions; keyword matches alone did not automatically confirm a course. General biology, generic professional ethics, ordinary business performance, and basic physical uses of energy are insufficient by themselves. For example, a 'sustainable competitive advantage' does not establish sustainability content. General health and cultural courses were not automatically included; explicit equity, social determinants, environmental protection or other relevant evidence was required. Foundational or ambiguous subjects and generic social-impact/project descriptions were generally left for review.

Course descriptions alone cannot establish the depth or assessed learning outcomes required by a particular STARS version. This screen uses a broad environmental-and-social understanding of sustainability, not an exclusively environmental definition. Before submission, use BYU's chosen STARS version and institutional curriculum-counting rules, and have relevant academic staff confirm the decisions.

## Preservation and evidence

All original fields are preserved verbatim. `original_row_number` identifies the original row. New columns use `assessment_` or `sustainability_` prefixes; the input's `manual_review_required` remains a source-data quality flag, separate from `sustainability_review_required`. Source-data quality flags take priority over inclusion even when the text suggests a connection. All 273 blank-description rows are in the review CSV, including the two rows with conflicting descriptions.

Duplicates, repeated course codes, variable titles and cross-listed courses were retained. Counts are input rows, not necessarily distinct offerings. The clear list can contain different titles for the same course code; use identifiers and institutional reporting rules before calculating a final STARS count. No invented descriptions or inferred syllabus contents were added.

The full description is quoted as evidence to avoid removing context. It is not a syllabus quotation and does not imply that every sentence is sustainability content. Classification rationale and theme identify the relevant connection.

## Validation

Checked exact preservation of every original field, input row count and order, mutually exclusive status totals, nonempty descriptions and exact evidence quotations for clear entries, and exclusion of unresolved source-quality records from the clear list. Only the supplied CSV was used as assessment evidence; no new website retrieval was needed.
