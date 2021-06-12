## Table of Contents

#### Insurance Industry Background

  * [Background of Industry](#background-of-industry)

  * [Threat Trends](#threat-trends)

#### Threat Modeling

  * [Critical Asset Identification](#critical-asset-identification)

  * [Diamond Models](#diamond-models)
    * [Model No 1](#model-no-1)
    * [Model No 2](#model-no-2)
    * [Model No 3](#model-no-3)
    * [Model No 4](#model-no-4)
    * [Model No 5](#model-no-5)

  * [Intelligence Buy In](#intelligence-buy-in)

#### Data Collection

  * [Data Sources Used](#data-sources-used)

  * [Data Collection Strategies](#data-collection-strategies)

  * [Data Samples](#data-samples)
    * [Censys](#censys-host-search)
    * [HostIntel](#hostintel-aggregator)

#### [About the Author](#about-me)

# Insurance Industry Background

## Background of Industry

Insurance is an arrangement by which a company provides a guarantee of compensation for specified loss, damages, or death in return for payment of a premium. There are two types of insurance, personal & commercial

**Personal Insurance**

* Property / Casualty
  * Auto
  * Home
* Life / Annuity
  * Health
  * Life

**Commercial Insurance**

* Property / Casualty
  * Worker's Compensation
  * Auto
  * Cyber Liability
  * Business Interruption

US Net Premiums in 2019 totaled $1.32 trillion. $638 billion was in property / casualty insurance, and $679 billion was in life / annuity insurance. There were approximately 6,000 companies in the US who sold insurance in 2019.

The following table is the top 5 property / casualty insurers in the US in 2019 (in millions):

|Company Name|Net Premiums written|
|---|---:|
|State Farm Group|$66.20|
|Berkshire Hathaway|$46.40|
|Progressive Insurance Group|$41.70|
|Allstate Insurance Group|$39.20|
|Liberty Mutual|$36.20|

<br>
[Back to Top][]

## Threat Trends

One of the common attacks against insurance agencies is phishing attempts. Bad actors attempt to gain access to private systems used by the insurance agency through phishing so they can steal personal information the insurer holds. Pretending to be a superior and other forms of social engineering are popular attacks on insurance agents.

Another issue regarding insurance data is that insurance companies will keep data from potential customers who are just looking for a quote but have not yet committed to an insurance company.  This greatly multiplies the number of potential victims as not only are customers impacted, but “window shoppers” attempting to compare prices will also be impacted by data breaches. This leads to an increase in attacks against insurance companies due to the larger amount of PII data.

Insiders using access to gather data and sell to competitors. Many insurance companies have a lack of logging or system access tools to prevent such an attack from occurring.

Ransomware attacks are on the rise for insurance companies. Preventing them from being able to conduct business, view customer data, or provide payouts to insurance claims can all decrease the public opinion of the insurer, which is one of an insurance company’s biggest assets. Because so much health information and personal information is shared with an insurer, the customer needs to feel they can trust the insurer with this sensitive data.

Convenience tools have been known to be attacked as well. Recently, websites that provide “instant quotes” to customers were hacked by entering a few pieces of information about someone and being able to steal unredacted driver’s license numbers.

<br>
[Back to Top][]

# Threat Modeling

## Critical Asset Identification

The following table lists 6 assets, their value to the company, what may occur as the result of a breach in that asset, and which user would be affected by such a breach.
<br>

|Asset|Value|Breach Penalty|User|
|---|---|---|---|
|Personally Identifiable Information (PII)|Allows the company to conduct its business regarding insurance eligibility and identification of an individual|Penalty is high. Loss of brand reputation, payouts to affected customers, 1-year of credit monitoring, etc.|Customer supplies information, underwriter uses to determine insurance worthiness|
|Personal Health Information (PHI)|Allows insurer of health or life insurance to determine eligibility requirements for various premium plans|Penalty is high. Compensation for leaked health records, and loss of brand reputation|Customer supplies information, underwriter uses it to determine insurance worthiness|
|Instant Quote Service|Allows company to automate providing insurance quotes, saving time and money|If system goes down due to attack, result is a loss in time to recover system and to provide quotes manually|Customer|
|Credit Card / Bank Information|Allows the company to request payments for premiums automatically|Compensation for any loss of funds for customers, loss of brand reputation|Customer enters information and can make payments. Financial may request payments through auto-pay|
|Mobile apps|Allows the company to push notifications to users and provide convenient access to user account details|Loss of functionality in app results in customer frustration, loss of competitive advantage from other companies with better apps|Customer|
|Network (servers and databases)|Automating communication and sending of information between underwriter and insurance agent|Loss of business time and revenue, impatient customers|Employees|

<br>
[Back to Top][]

## Diamond Models

Diamond models are used to help show the relationship between an adversary (cybercriminal), their victim, the infrastructure used to deploy the attack, and the capabilities required to make such an attack successful. Below are five diamond models for insurance.

### Model No 1

![Diamond Model No 1](https://user-images.githubusercontent.com/84549135/119081907-d3481a80-b9b1-11eb-925f-694aed3b76a2.png)

<br>
[Back to Top][]

### Model No 2

![Diamond Model No 2](https://user-images.githubusercontent.com/84549135/119081956-f246ac80-b9b1-11eb-918b-0890f2bcc537.png)

<br>
[Back to Top][]

### Model No 3

![Diamond Model No 3](https://user-images.githubusercontent.com/84549135/119081986-012d5f00-b9b2-11eb-8dac-522833dc2835.png)

<br>
[Back to Top][]

### Model No 4

![Diamond Model No 4](https://user-images.githubusercontent.com/84549135/119082016-0ee2e480-b9b2-11eb-86fc-7d9313c2c605.png)

<br>
[Back to Top][]

### Model No 5

![Diamond Model No 5](https://user-images.githubusercontent.com/84549135/119082047-1dc99700-b9b2-11eb-918b-04a1d6c57039.png)

<br>
[Back to Top][]

## Intelligence Buy In

The largest data breach in insurance history was Anthem Inc in 2015. This data breach affected 79 million records and cost Anthem approximately $391.5 million. This comes out to about $5 per record stolen. Considering this all came from a simple spear phishing email, creating a CTI platform and training a user on how to spot phishing attempts could have saved this company close to $390 million. A CTI platform will help boost preventative measures against phishing by staying up to date on the latest phishing attempts and other techniques used by bad actors.

<br>
[Back to Top][]

# Data Collection

## Data Sources Used

#### Censys

Censys is a search engine for internet connected devices. Censys performs scans on the internet daily to collect data about the types of devices are open and available for communication. This data is stored and freely available for querying by the public. Services such as this are compared to being a “google search engine for the internet of things”. Censys offers an API via Python to query its database and allow exporting of results to CSV and JSON. Users can query for:

* IPv4 Addresses
* Websites found on the Alexa One Million
* Certificates

The primary reason Censys was chosen, is because it boasts a highly functional and easy to use search feature to enhance data gathering techniques. This search tool was used to gather IP addresses for only those devices that are in the US, were updated within the last 2 years, and contain “insurance group” in the record. The purpose for using these search terms is to gather a list of IP addresses to plug into HostIntel, discussed next. Query structure used in the API:

* “insurance group” and location.country:”United States” and updated_at > 2019-06-11

#### HostIntel

HostIntel is a Python crawling tool developed by Keith Jones. This tool allows you to specific API keys for various intel resources, along with a list of IP addresses, and then crawl through each intel resource for each IP gathering various bits of data. These keys and IP addresses are configured into a few text files, and then a Python script is run to automate pulling data from the sources based on the IPs provided.

HostIntel makes acquiring data from multiple sources easy. HostIntel also allows you to configure your own modules for additional threat intelligence sources. These modules are added by adding new Python scripts for a given module, then calling that script from the main hostintel.py script. This function also allows you to remove threat intelligence sources that may not be useful. Lastly, the data gathered from HostIntel enables us to use machine learning to find trends in devices on the internet.

<br>
[Back to Top][]

## Data Collection Strategies

Censys was used as our initial query to gather a list of IP addresses to inspect with HostIntel. We used the search term “insurance group” to avoid finding results related to just “insurance”. For example, “insurance” pulled up results related to real estate companies, lawyers, etc. The purpose of this platform is to only look for data related to other insurance groups. This data was pulled using the API and only requesting for specific fields (see [Censys Host Search](#censys-host-search) data sample below).

The list of IP addresses from Censys was then used to perform the HostIntel search. This search aggregated data across VirusTotal, PassiveTotal, Shodan, and ThreatCrowd, and AlienVault. Once the data was combined, Censys data was appended into the master file. The result was then passed into a database for storing and further analysis.

<br>
[Back to Top][]

# Data Samples

## Censys Host Search

The table below is a snippet of the data stored in the database from the initial Censys Host Search. This data is later appended to the end of the HostIntel file. We have stored 846 data points. The primary reason this number is low is due to the limit of the API restricting how much data can be pulled. A search on the Censys reveals our query pulls around 7,000+ devices.

[censysresults_adjusted_v2.xlsx](https://github.com/shuskei/mis562milestone/files/6641826/censysresults_adjusted_v2.xlsx)

Data itself (50 rows minimum)

<br>
[Back to Top][]

## HostIntel Aggregator

Description of data - where it come from, how much data I have

Data itself (50 rows minimum)

<br>
[Back to Top][]

## About Me

Dylan Todd is a student at the University of Arizona. He has an M.S. degree in Management Information Systems, and is currently working on his M.S. in Cybersecurity. He is the sole contributor to this project. Please send any comments or feedback to dylantodd@arizona.edu.

<br>
[Back to Top][]

Page last updated: 7:01 PM MST on 06/07/2021

[Back to top]: #table-of-contents
