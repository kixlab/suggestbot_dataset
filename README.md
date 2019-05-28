# Online discussion and evidence dataset
From Internet Argument Corpus (IAC) 2.0 dataset, this dataset covers 10,000 posts containing claims that can be verified with facts. The dataset contains annotations on verifiable sentences for each post and factual information that supports or refutes each annotation.

The dataset is separated into Tab-Separated Value (TSV) files according to the topic of the discussion. Each TSV file has 22 fields, described as below.

1. evidence_id: ID for each piece of factual information
2. evidence_url: URL where the factual information was obtained
3. evidence_rawtext: The text of the factual information, found by the user
4. evidence_text: The text of the factual information, processed to match with the source text
5. query: The query string that the user used to obtained the factual information
6. type: The type of the factual information: 0 if testimonial, 1 if statistical, 2 if anecdotal
7. stance: 0 if this factual information supports the argument, 1 if it refutes the argument #TODO: field 순서 확인해주세요!
8. highlight_id: ID for each argument
9. user_id: ID of the user who found the factual information # TODO: 데이터셋에 있을 필요가 없는것같아요..
10. snippet_id_start: The sequence number of the first sentence of the argument
11. snippet_id_end: The sequence number of the last sentence of the argument
12. char_offset_start: dummy field
13. char_offset_end: dummy field
14. highlighted_phrase: Exact text of the argument
15. guideline: The guideline for finding related factual information for this argument, written by the user
16. highlight_user_id: ID of the user who found the argument #TODO: 역시 없어도 될 것 같아요
17. post_id: The ID of the post in the original IAC dataset
17. parent_id: The ID of the parent post, given in the original IAC dataset
18. topic: The topic of the discussion thread, given in the original IAC dataset
19. content: The exact text of the post
20. status