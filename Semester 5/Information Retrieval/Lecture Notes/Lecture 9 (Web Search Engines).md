#lectureNote
# Web Crawling

- Finds and downloads web pages automatically 
## Web Crawler
- It is a sw that _crawls_ the web collecting pages to put in the cash.
- Every page has a unique **uniform resource locator (URL)**.
- Process followed by a web crawler:
    -   Web crawler client program connects to a _Domain Name System (DNS)_ server
    -   DNS server translates the host name into an Internet Protocol (IP) address
    -   Crawler then attempts to connect to server host using specific port
    -   After connection, crawler sends an HTTP request to the web server to request a page.
        
        ## Major Crawling Strategies
        
-   Breadth-First is common
    
-   Parallel Crawling is natural
-   Variation:
    
    -   **Complete Crawling**
        -   Crawls everything you find
    -   **Focused Crawling**
        -   Targeting at a subset of pages
        -   Typically given a query
            
### Focused Crawling
            
- Attempts to download only those pages that are about a particular topic.
	-   Used by vertical search applications
-   Rely on the fact that pages about a topic tend to have links to other pages on the same ages on the same topic.
    
    ## Deep Web
    
-   Sites which are difficult for a crawler to find are collectively referred to as the deep
    
-   3 Board Categories:
    
    -   Private Sites
    -   Form Results
    -   Scripted Pages (JavaScript)
        
        ## Web Crawling Policies
        
-   To reduce inefficiency, web crawlers use threads and fetch hundreds of pages at once.
    
    ### Politeness Policies
    
-   Robots.txt file can be used to control crawlers and say which ones are allowed and which ones are not allowed.
    

# Ranking Algorithms for Web Search

-   They are used in order to find which websites are the most authoritative and generally better.
    
    ## Page Rank Algorithm
    
-   It is used to compute the **popularity** of the given web-pages. It does so by considering the websites inlinks.
    
-   The **Random Surfer Model** is the basic concept behind Page Rank.
    -   Chose a random number r between 0 and 1.
    -   if r < α, then go to a random page
    -   if r >= α, then click a link at random on the current page.
    -   Start again from beginning ![[Pasted image 20221211151250.png]]
-   Page Rank is essentially _citation counting_, but improves over simple counting.
-   Page Rank can also be interpreted as random surfing.
    
    ### Dangling Links
    
-   Random Jump prevents getting stuck on pages that
    
    -   Do not have links
    -   Contains only links that no longer point to other pages
    -   have links forming a loop
-   Dangling Links are as follows:
    
    -   **Do not have links**
    -   **Contains only links that no longer point to other pages**
        
        ### Page Rank and Link Quality
        
-   Page Rank can be deceived
    
-   Link Quality is affected by span and other factors
    
    -   Trackback links in blogs can create loops.
    -   Links from comment section of popular blogs.
        
        ## Hubs and Authorities
        
-   **HITS (Hypertext-Induced Topic Selection)**
    
    -   Hit is a measure of importance of pages or documents similar to Page Rank.
-   **Idea:** Links are Votes
    -   A page is more important if it has more links
-   Interesting pages fall into two classes:
    -   **Authorities** are pages containing useful information
    -   **Hubs** are pages that list a number of authorities
-   Each page has **two** scores, measuring
    -   _Quality as an expert (Hub)_
    -   _Quality of the content (Authority)_