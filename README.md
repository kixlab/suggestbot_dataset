# Online discussion and evidence dataset
From Internet Argument Corpus (IAC) 2.0 dataset, this dataset covers 10,000 posts containing claims that can be verified with facts. The dataset contains annotations on verifiable sentences for each post and factual information that supports or refutes each annotation.

The dataset is separated into three files (pharagraph.tsv, arguments.tsv, additionalinfo.tsv) and one folder (sourcedocs).

## posts.tsv
This TSV file has 5 fields, desvribed as below
1. post_id: The ID for each post, same with the ID of the post in IAC 2.0 dataset
2. post_topic: The topic of the discussion thread, given in the original IAC dataset
3. post_text: The text of the post
4. post_infoneed: 0 if the post does not need additional information, 1 if the post needs additional information

## arguments.tsv
This TSV file has 5 fields, described as below
1. arg_id: The ID for each highlighted argument 
2. arg_text: The text of the argument
3. arg_guideline: The guideline for finding related factual information for this argument, written by the user
4. arg_addinfo: 1 if the argument can be proved or disproved by additional information, 0 otherwise, evaluated by the user 
5. post_id: ID of the post that contains the argument
6. post_topic: The topic of the discussion thread, given in the original IAC dataset

## additionalinfo.tsv
This TSV file has 9 fields, described as below 
1. info_id: The ID for each peice of factual information
2. info_rawtext: The text of the factual information, found by the user
3. info_text: The text of the factual information, processed to match with the source text
4. info_url: URL where the factual information was obtained
5. info_query: The query string that the user used to obtained the factual information
6. info_type: The type of the factual information: 0 if testimonial, 1 if statistical, 2 if anecdotal
7. info_stance: 0 if this factual information supports the argument, 1 if it refutes the argument 
8. info_status: 'All' if the source page is parsed in tidy and untidy version. 'Untidy only' if the source page is parsed in untidy version only, 'None' if the source page is not accessible and not parsed. 
9. arg_id: ID of the argument that is supported or refuted by the information
10. arg_text: The content of the argument that is supported or refuted by the information
11. arg_guideline: The guideline for the argument that is supported or refuted by the information
12. post_id: The ID of the post in the original IAC dataset

## sourcedocs folder
The 'sourcedocs' folder contains parsed source pages of each additional information. There are two subfolder - tidy and untidy. 

### untidy folder
- In the 'untidy' folder, parsed source pages are stored in .txt format.
- Each source page is parsed using [Html2text](http://alir3z4.github.io/html2text/) package.
- The title of each txt file refers to the id of additional information (info_id). For example, '1.txt' contains parsed source page of url provided in the additional information with info_id=1. 

### tidy folder
- In the 'tidy' folder, also parsed source pages are stored in .txt format. 
- Each source page is parsed using [Html2text](http://alir3z4.github.io/html2text/) package and then [Newspaper3k](https://newspaper.readthedocs.io/en/latest/) package. 
- The title of each txt file refers to the id of additional information (info_id). For example, '1.txt' contains parsed source page of url provided in the additional information with info_id=1.