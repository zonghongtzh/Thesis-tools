# Thesis-tools
(directions to use will be posted below)

The codes have to be edited in a IDE, therefore users should ideally have Python IDEs to edit the script. (e.g. Anaconda, Sublime text)  

If you are urgent and without coding platforms, do drop me an email with the following: 

year_start = 

year_end = 

unique_url = 

page_navigation_url = 

keywords = 

compulsory_keywords = 

The step by step instructions to getting the above are below. 
I will edit the code and create an exe file for you to run the code without python

# Directions to use: Singapore Archives searcher.
To conduct primary/secondary source research for a Arts/Social Science thesis, students may need to sift through hundreds of thousands of newspaper articles from http://eresources.nlb.gov.sg/newspapers/. To do this, students first:
1. Conduct a keyword search
2. Check the relevent filter boxes
3. read through the preview paragraph to decide whether it might be relevant
4. click on potential relevant articles to read full article, then decide final relevance

To streamline this process, Arts_reserch_tools attempts to automate part 3. When a student reads the preview paragraph, the student is looking out for keywords and phrases which may indicate relevance. 

### Step by step example for "opinions towards english language" research
### Steps:
### 1. Student conducts a keyword search for "english language"

### 2. Student checks relevant filter boxes:

- Viewable from home
- The Straits Times
- Today 
- Singapore Herald
- Articles
- Letters
- Word Count, 50-300
- DO NOT CLICK "Year" CHECKBOXES

### 3. click "Filter"

copy link at URL:
http://eresources.nlb.gov.sg/newspapers/Digitised/Search?ST=1&AT=filter&K=english+language&KA=english+language&DF=&DT=&Display=0&AO=true&NPT=&L=&CTA=&NID=straitstimes|singherald&CT=ARTICLE|LETTER&WC=From51To300&YR=

The link is important as it contains the unique filters applied to the search, and at the end of the link, it asks for the year of interest (at "YR="). 

### 4. Decide years of interest:

e.g. year_start = 1953, year_end = 1987

### 5. press the "Next" arrow to navigate to the next page, this is done so as to record the URL for page navigation
(Potential inefficiencies with the code here unfortunately, but it is the simplest way so far. Problems are encountered when page has no "Next" button). 

copy link at URL: http://eresources.nlb.gov.sg/newspapers/Digitised/Search?ST=1&AT=filter&DF=&DT=&AO=true&NPT=&L=&CTA=&NID=straitstimes%7csingherald&CT=ARTICLE%7cLETTER&WC=From51To300&YR=&k=english%20language&ka=english%20language&P=2&Display=0&filterS=0

This link contains the navigation function "P=2&Display=0&filterS=0" at the end of the URL where P=2 is essentially page 2, varying the numbers will vary the pages itself.

### 6. Edit the code:

Line 1: year_start = 1953

Line 2: year_end = 1987

Line 3: unique_url = "http://eresources.nlb.gov.sg/newspapers/Digitised/Search?ST=1&AT=filter&K=%E5%8D%8E%E6%96%87&KA=%E5%8D%8E%E6%96%87&DF=&DT=&Display=0&AO=true&NPT=&L=&CTA=&NID=lhzb|nysp|scjp&CT=ARTICLE&WC=From51To300&YR="

Line 4: page_navigation_url = "http://eresources.nlb.gov.sg/newspapers/Digitised/Search?ST=1&AT=filter&DF=&DT=&AO=true&NPT=&L=&CTA=&NID=straitstimes%7csingherald&CT=ARTICLE%7cLETTER&WC=From51To300&YR=1960&k=english%20language&ka=english%20language&P=2&Display=0&filterS=0"

For line 3 and 4, open and closed inverted commas must be used at the front and back of the URL

### 7. Determining keywords to validate usefulness of articles

This is the most crucial part of the search and it is split into two segments. By varying the keywords or symbols, the webcrawler will pick up different articles as "potentially useful".

For example, i would like to know the opinions towards english language, i would therefore like to see things that are said by politicians or by people in general. therefore i may input:

Line 5: keywords = ['"', "'", "Lee", "USING", "说", "說", "say", "said", "saying"]

Line 6: compulsory_keywords = ["english", "English"] 

Take note that:
- All keywords must have open and closed inverted commas. (either '{item}' or "{item}")
- Capitalization matters, "say" and "Say" are different and both must be put in to guarantee the pick up 
- Chinese words should be put in simplified and traditional because most of the archive's chinese newspaper use traditional chinese. 

compulsory_keywords are special keywords. IF the user wants to further narrow their search, they can mandate that unless the preview paragraph contains the compulsory_keywords, the entire paragraph will not be picked up even if it contains keywords. 

To leave compulsory_keywords blank, use: 

compulsory_keywords = [""]

### 8. Run code
upon completion, save and run code


Post-script notes: Will create a user-input version soon 





