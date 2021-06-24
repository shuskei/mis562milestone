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

#### Data Analytics

  * [Anomaly Detection](#anomaly-detection)

  * [IP Reputation](#ip-reputation)

  * [Shodan Tag Correlation](#shodan-tag-correlation)
  
  * [Key Insights](#key-insights)

#### Visual Aids

  * [Censys Port Cloud](#censys-port-cloud)
  
  * [IP Location](#ip-location)

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

|ip             |autonomous\_system.name    |updated\_at              |protocols                                                                                                                                       |443.https.get.metadata.description                                                                                                                                                                                                                     |443.https.tls.certificate.parsed.names                                                                            |443.https.tls.certificate.parsed.subject\_dn                                                    |
|---------------|---------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
|192.163.226.184|UNIFIEDLAYER-AS-1          |2021-06-09T11:36:36+00:00|\['80/http', '3306/mysql', '993/imaps', '995/pop3s', '110/pop3', '143/imap', '53/dns', '587/smtp', '443/https', '22/ssh'\]                      |Apache httpd                                                                                                                                                                                                                                           |\['landlordinsuranceqts.com', 'mail.landlordinsuranceqts.com', 'www.landlordinsuranceqts.com'\]                   |CN=landlordinsuranceqts.com                                                                     |
|76.190.87.142  |TWC-10796-MIDWEST          |2021-06-09T13:43:22+00:00|\['443/https'\]                                                                                                                                 |\['mmr.cai-insurance.com', '76.190.87.142'\]                                                                                                                                                                                                           |C=US, ST=Ohio, L=Cincinnati, O=CAI Insurance, OU=CAI Insurance, CN=mmr.cai-insurance.com                          |
|24.154.239.180 |ACS-INTERNET               |2021-06-09T12:18:20+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|76.190.87.139  |TWC-10796-MIDWEST          |2021-06-09T09:33:05+00:00|\['443/https'\]                                                                                                                                 |\['rast.cai-insurance.com', '10.10.10.2'\]                                                                                                                                                                                                             |C=US, ST=Ohio, L=Cincinnati, O=CAI Insurance, OU=CAI Insurance, CN=rast.cai-insurance.com                         |
|68.170.153.205 |FDS-01                     |2021-06-09T07:21:58+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft IIS 10.0                                                                                                                                                                                                                                     |\['localhost'\]                                                                                                   |CN=localhost                                                                                    |
|68.170.153.197 |FDS-01                     |2021-06-09T07:43:25+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft IIS 8.5                                                                                                                                                                                                                                      |\['\*.certrax.com', 'certrax.com'\]                                                                               |OU=Domain Control Validated, CN=\*.certrax.com                                                  |
|162.144.34.14  |UNIFIEDLAYER-AS-1          |2021-06-09T12:54:23+00:00|\['80/http', '3306/mysql', '993/imaps', '995/pop3s', '110/pop3', '143/imap', '53/dns', '587/smtp', '443/https', '22/ssh'\]                      |Apache httpd                                                                                                                                                                                                                                           |\['fireinsuranceqts.com', 'mail.fireinsuranceqts.com', 'www.fireinsuranceqts.com'\]                               |CN=fireinsuranceqts.com                                                                         |
|45.40.182.97   |GO-DADDY-COM-LLC           |2021-06-09T07:40:53+00:00|\['443/https', '80/http', '21/ftp'\]                                                                                                            |Apache httpd                                                                                                                                                                                                                                           |\['www.alphaomegaia.com', 'alphaomegaia.com'\]                                                                    |OU=Domain Control Validated, CN=www.alphaomegaia.com                                            |
|173.201.222.103|AS-26496-GO-DADDY-COM-LLC  |2021-06-09T10:43:07+00:00|\['443/https', '22/ssh', '21/ftp', '80/http'\]                                                                                                  |Apache httpd                                                                                                                                                                                                                                           |                                                                                                                  |
|216.92.169.7   |PAIR-NETWORKS              |2021-06-09T11:46:28+00:00|\['80/http', '22/ssh', '21/ftp'\]                                                                                                               |                                                                                                                                                                                                                                                       |
|108.36.166.172 |UUNET                      |2021-06-09T13:37:01+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|68.170.153.201 |FDS-01                     |2021-06-09T08:45:08+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft IIS 10.0                                                                                                                                                                                                                                     |\['\*.certrax.com', 'certrax.com'\]                                                                               |CN=\*.certrax.com                                                                               |
|138.43.224.33  |MVLINK                     |2021-06-09T11:15:56+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|72.95.32.5     |UUNET                      |2021-06-08T08:01:51+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|104.248.176.194|DIGITALOCEAN-ASN           |2021-06-09T08:35:10+00:00|\['443/https', '22/ssh', '80/http'\]                                                                                                            |nginx 1.14.0                                                                                                                                                                                                                                           |\['www.ho6insurance.com', 'ho6insurance.com'\]                                                                    |CN=ho6insurance.com                                                                             |
|207.228.234.189|HOPONE-GLOBAL              |2021-06-09T11:51:38+00:00|\['80/http', '21/ftp'\]                                                                                                                         |                                                                                                                                                                                                                                                       |                                                                                                                  |
|50.63.113.83   |GO-DADDY-COM-LLC           |2021-06-09T09:54:47+00:00|\['80/http', '21/ftp'\]                                                                                                                         |                                                                                                                                                                                                                                                       |                                                                                                                  |
|23.99.83.18    |MICROSOFT-CORP-MSN-AS-BLOCK|2021-06-09T10:21:11+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft HTTPAPI 2.0                                                                                                                                                                                                                                  |\['api.culverinsurance.net', 'www.api.culverinsurance.net'\]                                                      |CN=api.culverinsurance.net                                                                      |
|8.20.77.209    |LEVEL3                     |2021-06-09T08:07:34+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|12.7.103.5     |ATT-INTERNET4              |2021-06-09T13:31:12+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|54.145.226.166 |AMAZON-AES                 |2021-06-09T08:17:20+00:00|\['443/https'\]                                                                                                                                 |nginx 1.12.2                                                                                                                                                                                                                                           |                                                                                                                  |
|45.79.173.180  |LINODE-AP Linode, LLC      |2021-06-09T13:56:34+00:00|\['80/http', '3306/mysql', '993/imaps', '465/smtp', '995/pop3s', '110/pop3', '21/ftp', '143/imap', '53/dns', '587/smtp', '443/https', '22/ssh'\]|Apache httpd                                                                                                                                                                                                                                           |\['healthquoteinfo.com', 'www.healthquoteinfo.com'\]                                                              |OU=Domain Control Validated, CN=healthquoteinfo.com                                             |
|66.194.26.58   |LVLT-3549                  |2021-06-08T06:43:13+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|54.83.132.51   |AMAZON-AES                 |2021-06-09T13:34:01+00:00|\['443/https', '80/http'\]                                                                                                                      |nginx                                                                                                                                                                                                                                                  |\['www.puppymatch4you.com', 'puppymatch4you.com'\]                                                                |CN=www.puppymatch4you.com                                                                       |
|52.202.26.234  |AMAZON-AES                 |2021-06-09T07:35:30+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft HTTPAPI 2.0                                                                                                                                                                                                                                  |\['dev.pekininsurance.com'\]                                                                                      |O=Pekin Insurance, OU=Enterprise Security, C=US, ST=Illinois, L=Pekin, CN=dev.pekininsurance.com|
|207.97.195.85  |RACKSPACE                  |2021-06-09T08:40:34+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|23.99.87.75    |MICROSOFT-CORP-MSN-AS-BLOCK|2021-06-09T07:01:02+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft IIS 10.0                                                                                                                                                                                                                                     |\['www.motorcycleinsuranceus.com', 'motorcycleinsuranceus.com'\]                                                  |CN=www.motorcycleinsuranceus.com                                                                |
|132.148.60.119 |GO-DADDY-COM-LLC           |2021-06-09T10:39:13+00:00|\['443/https', '22/ssh', '21/ftp', '80/http'\]                                                                                                  |Apache httpd                                                                                                                                                                                                                                           |\['alphaomegaia.com', 'www.alphaomegaia.com'\]                                                                    |OU=Domain Control Validated, CN=www.alphaomegaia.com                                            |
|173.248.91.200 |SHELTERCUSTOMER            |2021-06-09T14:17:20+00:00|\['443/https'\]                                                                                                                                 |\['acemp.shelterinsurance.com', 'ac2fa.shelterinsurance.com', 'ac2fa2.shelterinsurance.com', 'ac2fa3.shelterinsurance.com', 'ac2fa4.shelterinsurance.com', 'ac2fa5.shelterinsurance.com', 'ac2fa6.shelterinsurance.com', 'acpci.shelterinsurance.com'\]|C=US, ST=MO, L=Columbia, O=Shelter Insurance                                                                      |
|54.152.86.39   |AMAZON-AES                 |2021-06-09T09:41:47+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|216.92.86.190  |PAIR-NETWORKS              |2021-06-09T06:55:03+00:00|\['80/http', '22/ssh', '21/ftp'\]                                                                                                               |                                                                                                                                                                                                                                                       |
|76.190.87.141  |TWC-10796-MIDWEST          |2021-06-09T08:53:16+00:00|\['443/https'\]                                                                                                                                 |\['rp.cai-insurance.com'\]                                                                                                                                                                                                                             |C=US, ST=Ohio, L=Cincinnati, O=CAI Insurance, OU=CAI Insurance, CN=rp.cai-insurance.com                           |
|216.92.231.25  |PAIR-NETWORKS              |2021-06-09T09:08:33+00:00|\['80/http', '22/ssh', '21/ftp'\]                                                                                                               |                                                                                                                                                                                                                                                       |
|54.243.109.226 |AMAZON-AES                 |2021-06-09T09:26:23+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|216.48.108.39  |NOCTURNAL                  |2021-06-09T08:53:45+00:00|\['443/https', '80/http'\]                                                                                                                      |Microsoft IIS 6.0                                                                                                                                                                                                                                      |\['www.smsinsuranceagency.com', 'smsinsuranceagency.com'\]                                                        |CN=www.smsinsuranceagency.com                                                                   |
|50.225.135.237 |COMCAST-7922               |2021-06-09T10:29:49+00:00|\['443/https'\]                                                                                                                                 |\['mrtr.wolverinemutual.com', '50.225.135.237'\]                                                                                                                                                                                                       |C=US, ST=Michigan, L=Dowagiac, O=Wolverine Mutual Insurance Company, OU=IT Department, CN=mrtr.wolverinemutual.com|
|174.99.166.12  |TWC-11426-CAROLINAS        |2021-06-09T10:28:00+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|72.22.86.124   |NETSOURCE                  |2021-06-09T07:37:02+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|174.99.166.10  |TWC-11426-CAROLINAS        |2021-06-09T11:54:28+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|72.22.86.122   |NETSOURCE                  |2021-06-09T07:30:15+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|216.119.122.146|CENTURYLINK-LEGACY-LVLT-203|2021-06-09T07:47:41+00:00|\['80/http', '21/ftp'\]                                                                                                                         |                                                                                                                                                                                                                                                       |                                                                                                                  |
|199.102.8.164  |MERCURYINS                 |2021-06-09T11:05:12+00:00|\['443/https', '80/http'\]                                                                                                                      |\['secure.agentzone.biz'\]                                                                                                                                                                                                                             |C=US, ST=California, L=Brea, O=Mercury Insurance Company, OU=IT, CN=secure.agentzone.biz                          |
|72.95.32.6     |UUNET                      |2021-06-09T09:29:39+00:00|\['587/smtp', '465/smtp', '25/smtp'\]                                                                                                           |
|34.235.103.47  |AMAZON-AES                 |2021-06-09T12:00:34+00:00|\['80/http'\]                                                                                                                                   |                                                                                                                                                                                                                                                       |                                                                                                                  |
|209.169.7.221  |EARTHNET                   |2021-06-08T09:47:18+00:00|\['80/http', '21/ftp'\]                                                                                                                         |                                                                                                                                                                                                                                                       |                                                                                                                  |
|207.178.244.75 |AS5033                     |2021-06-10T07:13:50+00:00|\['443/https', '80/http'\]                                                                                                                      |nginx                                                                                                                                                                                                                                                  |\['\*.cloud-insurance-software.com', 'cloud-insurance-software.com'\]                                             |OU=Domain Control Validated, CN=\*.cloud-insurance-software.com                                 |
|52.1.75.210    |AMAZON-AES                 |2021-06-10T07:22:03+00:00|\['443/https', '80/http'\]                                                                                                                      |nginx 1.12.2                                                                                                                                                                                                                                           |\['\*.everquote.com', 'everquote.com'\]                                                                           |CN=everquote.com                                                                                |
|96.83.208.170  |COMCAST-7922               |2021-06-09T12:53:43+00:00|\['443/https'\]                                                                                                                                 |\['50.246.168.4'\]                                                                                                                                                                                                                                     |C=US, ST=Pennsylvania, L=Horsham, O=Penn Mutual Life Insurance Company, CN=50.246.168.4                           |
|66.195.73.150  |LEVEL3                     |2021-06-08T08:32:23+00:00|\['80/http', '21/ftp'\]                                                                                                                         |                                                                                                                                                                                                                                                       |                                                                                                                  |
|204.132.81.133 |CENTURYLINK-US-LEGACY-QWEST|2021-06-09T09:56:32+00:00|\['443/https'\]                                                                                                                                 |\['mobility.priceramey.com', '204.132.81.133', '192.168.16.80'\]                                                                                                                                                                                       |C=US, ST=Tennessee, L=Kingsport, O=Insurance, OU=Price Ramey, CN=mobility.priceramey.com                          |

<br>
[Back to Top][]

## HostIntel Aggregator

The table below is a snippet of the data stored in the database from the HostIntel scripts. We have stored 511 data points. The primary reason this number is low is due to the limit of the API restricting how much data can be pulled. The resulting number here should be exact to the result from Censys without API restrictions.

|Input Host     |VT # URLs|VT Comm. Samples|VirusTotal Link                                                      |PT Enrichment Sinkhole|PT Enrichment Ever Compromised|PT # Malware|PT OSInt Samples|Shodan Tags                           |Shodan URL                                |ThreatCrowd URL                                      |ThreatCrowd Number of Hashes|ThreatCrowd Number of Resolutions|ThreatCrowd Number of Subdomains|OTX URL                                                |OTX General Whois                           |OTX General DMA Code|
|---------------|---------|----------------|---------------------------------------------------------------------|----------------------|------------------------------|------------|----------------|--------------------------------------|------------------------------------------|-----------------------------------------------------|----------------------------|---------------------------------|--------------------------------|-------------------------------------------------------|--------------------------------------------|--------------------|
|192.163.226.184|0        |0               |https://www.virustotal.com/en/ip-address/192.163.226.184/information/|FALSE                 |FALSE                         |0           |0               |database; starttls                    |https://www.shodan.io/host/192.163.226.184|https://www.threatcrowd.org/ip.php?ip=192.163.226.184|0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/192.163.226.184|http://whois.domaintools.com/192.163.226.184|0                   |
|76.190.87.142  |0        |0               |https://www.virustotal.com/en/ip-address/76.190.87.142/information/  |FALSE                 |FALSE                         |0           |0               |                                      |No information available for that IP.     |https://www.threatcrowd.org/ip.php?ip=76.190.87.142  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/76.190.87.142  |http://whois.domaintools.com/76.190.87.142  |541                 |
|24.154.239.180 |0        |0               |https://www.virustotal.com/en/ip-address/24.154.239.180/information/ |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/24.154.239.180 |https://www.threatcrowd.org/ip.php?ip=24.154.239.180 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/24.154.239.180 |http://whois.domaintools.com/24.154.239.180 |508                 |
|76.190.87.139  |0        |0               |https://www.virustotal.com/en/ip-address/76.190.87.139/information/  |FALSE                 |FALSE                         |0           |0               |                                      |No information available for that IP.     |https://www.threatcrowd.org/ip.php?ip=76.190.87.139  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/76.190.87.139  |http://whois.domaintools.com/76.190.87.139  |541                 |
|68.170.153.205 |0        |0               |https://www.virustotal.com/en/ip-address/68.170.153.205/information/ |FALSE                 |FALSE                         |0           |0               |                                      |No information available for that IP.     |https://www.threatcrowd.org/ip.php?ip=68.170.153.205 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/68.170.153.205 |http://whois.domaintools.com/68.170.153.205 |501                 |
|68.170.153.197 |0        |0               |https://www.virustotal.com/en/ip-address/68.170.153.197/information/ |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/68.170.153.197 |https://www.threatcrowd.org/ip.php?ip=68.170.153.197 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/68.170.153.197 |http://whois.domaintools.com/68.170.153.197 |501                 |
|162.144.34.14  |0        |0               |https://www.virustotal.com/en/ip-address/162.144.34.14/information/  |FALSE                 |FALSE                         |0           |0               |starttls; database                    |https://www.shodan.io/host/162.144.34.14  |https://www.threatcrowd.org/ip.php?ip=162.144.34.14  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/162.144.34.14  |http://whois.domaintools.com/162.144.34.14  |0                   |
|45.40.182.97   |0        |0               |https://www.virustotal.com/en/ip-address/45.40.182.97/information/   |FALSE                 |FALSE                         |0           |0               |self-signed; starttls                 |https://www.shodan.io/host/45.40.182.97   |https://www.threatcrowd.org/ip.php?ip=45.40.182.97   |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/45.40.182.97   |http://whois.domaintools.com/45.40.182.97   |0                   |
|173.201.222.103|0        |1               |https://www.virustotal.com/en/ip-address/173.201.222.103/information/|FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/173.201.222.103|https://www.threatcrowd.org/ip.php?ip=173.201.222.103|0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/173.201.222.103|http://whois.domaintools.com/173.201.222.103|0                   |
|216.92.169.7   |0        |0               |https://www.virustotal.com/en/ip-address/216.92.169.7/information/   |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/216.92.169.7   |https://www.threatcrowd.org/ip.php?ip=216.92.169.7   |0                           |1                                |0                               |https://otx.alienvault.com/indicator/ip/216.92.169.7   |http://whois.domaintools.com/216.92.169.7   |0                   |
|108.36.166.172 |0        |0               |https://www.virustotal.com/en/ip-address/108.36.166.172/information/ |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/108.36.166.172 |https://www.threatcrowd.org/ip.php?ip=108.36.166.172 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/108.36.166.172 |http://whois.domaintools.com/108.36.166.172 |504                 |
|68.170.153.201 |0        |0               |https://www.virustotal.com/en/ip-address/68.170.153.201/information/ |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/68.170.153.201 |https://www.threatcrowd.org/ip.php?ip=68.170.153.201 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/68.170.153.201 |http://whois.domaintools.com/68.170.153.201 |501                 |
|138.43.224.33  |0        |0               |https://www.virustotal.com/en/ip-address/138.43.224.33/information/  |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/138.43.224.33  |https://www.threatcrowd.org/ip.php?ip=138.43.224.33  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/138.43.224.33  |http://whois.domaintools.com/138.43.224.33  |637                 |
|72.95.32.5     |0        |0               |https://www.virustotal.com/en/ip-address/72.95.32.5/information/     |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/72.95.32.5     |https://www.threatcrowd.org/ip.php?ip=72.95.32.5     |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/72.95.32.5     |http://whois.domaintools.com/72.95.32.5     |566                 |
|104.248.176.194|0        |0               |https://www.virustotal.com/en/ip-address/104.248.176.194/information/|FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/104.248.176.194|https://www.threatcrowd.org/ip.php?ip=104.248.176.194|0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/104.248.176.194|http://whois.domaintools.com/104.248.176.194|807                 |
|207.228.234.189|0        |0               |https://www.virustotal.com/en/ip-address/207.228.234.189/information/|FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/207.228.234.189|https://www.threatcrowd.org/ip.php?ip=207.228.234.189|0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/207.228.234.189|http://whois.domaintools.com/207.228.234.189|0                   |
|50.63.113.83   |0        |0               |https://www.virustotal.com/en/ip-address/50.63.113.83/information/   |FALSE                 |FALSE                         |0           |0               |self-signed; starttls                 |https://www.shodan.io/host/50.63.113.83   |https://www.threatcrowd.org/ip.php?ip=50.63.113.83   |0                           |1                                |0                               |https://otx.alienvault.com/indicator/ip/50.63.113.83   |http://whois.domaintools.com/50.63.113.83   |0                   |
|23.99.83.18    |0        |0               |https://www.virustotal.com/en/ip-address/23.99.83.18/information/    |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/23.99.83.18    |https://www.threatcrowd.org/ip.php?ip=23.99.83.18    |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/23.99.83.18    |http://whois.domaintools.com/23.99.83.18    |807                 |
|8.20.77.209    |0        |0               |https://www.virustotal.com/en/ip-address/8.20.77.209/information/    |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/8.20.77.209    |https://www.threatcrowd.org/ip.php?ip=8.20.77.209    |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/8.20.77.209    |http://whois.domaintools.com/8.20.77.209    |0                   |
|12.7.103.5     |0        |0               |https://www.virustotal.com/en/ip-address/12.7.103.5/information/     |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/12.7.103.5     |https://www.threatcrowd.org/ip.php?ip=12.7.103.5     |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/12.7.103.5     |http://whois.domaintools.com/12.7.103.5     |650                 |
|54.145.226.166 |0        |0               |https://www.virustotal.com/en/ip-address/54.145.226.166/information/ |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/54.145.226.166 |https://www.threatcrowd.org/ip.php?ip=54.145.226.166 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/54.145.226.166 |http://whois.domaintools.com/54.145.226.166 |511                 |
|45.79.173.180  |0        |0               |https://www.virustotal.com/en/ip-address/45.79.173.180/information/  |FALSE                 |FALSE                         |0           |0               |database; self-signed; cloud; starttls|https://www.shodan.io/host/45.79.173.180  |https://www.threatcrowd.org/ip.php?ip=45.79.173.180  |0                           |2                                |0                               |https://otx.alienvault.com/indicator/ip/45.79.173.180  |http://whois.domaintools.com/45.79.173.180  |501                 |
|66.194.26.58   |0        |0               |https://www.virustotal.com/en/ip-address/66.194.26.58/information/   |FALSE                 |FALSE                         |0           |0               |vpn; starttls                         |https://www.shodan.io/host/66.194.26.58   |https://www.threatcrowd.org/ip.php?ip=66.194.26.58   |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/66.194.26.58   |http://whois.domaintools.com/66.194.26.58   |546                 |
|54.83.132.51   |0        |0               |https://www.virustotal.com/en/ip-address/54.83.132.51/information/   |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/54.83.132.51   |https://www.threatcrowd.org/ip.php?ip=54.83.132.51   |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/54.83.132.51   |http://whois.domaintools.com/54.83.132.51   |511                 |
|52.202.26.234  |0        |0               |https://www.virustotal.com/en/ip-address/52.202.26.234/information/  |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/52.202.26.234  |https://www.threatcrowd.org/ip.php?ip=52.202.26.234  |0                           |1                                |0                               |https://otx.alienvault.com/indicator/ip/52.202.26.234  |http://whois.domaintools.com/52.202.26.234  |511                 |
|207.97.195.85  |0        |0               |https://www.virustotal.com/en/ip-address/207.97.195.85/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/207.97.195.85  |https://www.threatcrowd.org/ip.php?ip=207.97.195.85  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/207.97.195.85  |http://whois.domaintools.com/207.97.195.85  |0                   |
|23.99.87.75    |0        |0               |https://www.virustotal.com/en/ip-address/23.99.87.75/information/    |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/23.99.87.75    |https://www.threatcrowd.org/ip.php?ip=23.99.87.75    |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/23.99.87.75    |http://whois.domaintools.com/23.99.87.75    |807                 |
|132.148.60.119 |0        |0               |https://www.virustotal.com/en/ip-address/132.148.60.119/information/ |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/132.148.60.119 |https://www.threatcrowd.org/ip.php?ip=132.148.60.119 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/132.148.60.119 |http://whois.domaintools.com/132.148.60.119 |819                 |
|173.248.91.200 |0        |0               |https://www.virustotal.com/en/ip-address/173.248.91.200/information/ |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/173.248.91.200 |https://www.threatcrowd.org/ip.php?ip=173.248.91.200 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/173.248.91.200 |http://whois.domaintools.com/173.248.91.200 |0                   |
|54.152.86.39   |0        |0               |https://www.virustotal.com/en/ip-address/54.152.86.39/information/   |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/54.152.86.39   |https://www.threatcrowd.org/ip.php?ip=54.152.86.39   |0                           |1                                |0                               |https://otx.alienvault.com/indicator/ip/54.152.86.39   |http://whois.domaintools.com/54.152.86.39   |511                 |
|216.92.86.190  |0        |0               |https://www.virustotal.com/en/ip-address/216.92.86.190/information/  |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/216.92.86.190  |https://www.threatcrowd.org/ip.php?ip=216.92.86.190  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/216.92.86.190  |http://whois.domaintools.com/216.92.86.190  |0                   |
|76.190.87.141  |0        |0               |https://www.virustotal.com/en/ip-address/76.190.87.141/information/  |FALSE                 |FALSE                         |0           |0               |self-signed                           |https://www.shodan.io/host/76.190.87.141  |https://www.threatcrowd.org/ip.php?ip=76.190.87.141  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/76.190.87.141  |http://whois.domaintools.com/76.190.87.141  |541                 |
|216.92.231.25  |0        |0               |https://www.virustotal.com/en/ip-address/216.92.231.25/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/216.92.231.25  |https://www.threatcrowd.org/ip.php?ip=216.92.231.25  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/216.92.231.25  |http://whois.domaintools.com/216.92.231.25  |0                   |
|54.243.109.226 |0        |0               |https://www.virustotal.com/en/ip-address/54.243.109.226/information/ |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/54.243.109.226 |https://www.threatcrowd.org/ip.php?ip=54.243.109.226 |0                           |10                               |0                               |https://otx.alienvault.com/indicator/ip/54.243.109.226 |http://whois.domaintools.com/54.243.109.226 |511                 |
|216.48.108.39  |0        |0               |https://www.virustotal.com/en/ip-address/216.48.108.39/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/216.48.108.39  |https://www.threatcrowd.org/ip.php?ip=216.48.108.39  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/216.48.108.39  |http://whois.domaintools.com/216.48.108.39  |0                   |
|50.225.135.237 |0        |0               |https://www.virustotal.com/en/ip-address/50.225.135.237/information/ |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/50.225.135.237 |https://www.threatcrowd.org/ip.php?ip=50.225.135.237 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/50.225.135.237 |http://whois.domaintools.com/50.225.135.237 |819                 |
|174.99.166.12  |0        |0               |https://www.virustotal.com/en/ip-address/174.99.166.12/information/  |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/174.99.166.12  |https://www.threatcrowd.org/ip.php?ip=174.99.166.12  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/174.99.166.12  |http://whois.domaintools.com/174.99.166.12  |546                 |
|72.22.86.124   |0        |0               |https://www.virustotal.com/en/ip-address/72.22.86.124/information/   |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/72.22.86.124   |https://www.threatcrowd.org/ip.php?ip=72.22.86.124   |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/72.22.86.124   |http://whois.domaintools.com/72.22.86.124   |0                   |
|174.99.166.10  |0        |0               |https://www.virustotal.com/en/ip-address/174.99.166.10/information/  |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/174.99.166.10  |https://www.threatcrowd.org/ip.php?ip=174.99.166.10  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/174.99.166.10  |http://whois.domaintools.com/174.99.166.10  |546                 |
|72.22.86.122   |0        |0               |https://www.virustotal.com/en/ip-address/72.22.86.122/information/   |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/72.22.86.122   |https://www.threatcrowd.org/ip.php?ip=72.22.86.122   |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/72.22.86.122   |http://whois.domaintools.com/72.22.86.122   |0                   |
|216.119.122.146|0        |0               |https://www.virustotal.com/en/ip-address/216.119.122.146/information/|FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/216.119.122.146|https://www.threatcrowd.org/ip.php?ip=216.119.122.146|0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/216.119.122.146|http://whois.domaintools.com/216.119.122.146|0                   |
|199.102.8.164  |0        |0               |https://www.virustotal.com/en/ip-address/199.102.8.164/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/199.102.8.164  |https://www.threatcrowd.org/ip.php?ip=199.102.8.164  |0                           |2                                |0                               |https://otx.alienvault.com/indicator/ip/199.102.8.164  |http://whois.domaintools.com/199.102.8.164  |0                   |
|72.95.32.6     |0        |0               |https://www.virustotal.com/en/ip-address/72.95.32.6/information/     |FALSE                 |FALSE                         |0           |0               |starttls                              |https://www.shodan.io/host/72.95.32.6     |https://www.threatcrowd.org/ip.php?ip=72.95.32.6     |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/72.95.32.6     |http://whois.domaintools.com/72.95.32.6     |566                 |
|34.235.103.47  |0        |0               |https://www.virustotal.com/en/ip-address/34.235.103.47/information/  |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/34.235.103.47  |https://www.threatcrowd.org/ip.php?ip=34.235.103.47  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/34.235.103.47  |http://whois.domaintools.com/34.235.103.47  |511                 |
|209.169.7.221  |0        |0               |https://www.virustotal.com/en/ip-address/209.169.7.221/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/209.169.7.221  |https://www.threatcrowd.org/ip.php?ip=209.169.7.221  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/209.169.7.221  |http://whois.domaintools.com/209.169.7.221  |0                   |
|207.178.244.75 |0        |0               |https://www.virustotal.com/en/ip-address/207.178.244.75/information/ |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/207.178.244.75 |https://www.threatcrowd.org/ip.php?ip=207.178.244.75 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/207.178.244.75 |http://whois.domaintools.com/207.178.244.75 |0                   |
|52.1.75.210    |0        |0               |https://www.virustotal.com/en/ip-address/52.1.75.210/information/    |FALSE                 |FALSE                         |0           |0               |cloud                                 |https://www.shodan.io/host/52.1.75.210    |https://www.threatcrowd.org/ip.php?ip=52.1.75.210    |0                           |1                                |0                               |https://otx.alienvault.com/indicator/ip/52.1.75.210    |http://whois.domaintools.com/52.1.75.210    |511                 |
|96.83.208.170  |0        |0               |https://www.virustotal.com/en/ip-address/96.83.208.170/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/96.83.208.170  |https://www.threatcrowd.org/ip.php?ip=96.83.208.170  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/96.83.208.170  |http://whois.domaintools.com/96.83.208.170  |504                 |
|66.195.73.150  |0        |0               |https://www.virustotal.com/en/ip-address/66.195.73.150/information/  |FALSE                 |FALSE                         |0           |0               |                                      |https://www.shodan.io/host/66.195.73.150  |https://www.threatcrowd.org/ip.php?ip=66.195.73.150  |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/66.195.73.150  |http://whois.domaintools.com/66.195.73.150  |0                   |
|204.132.81.133 |0        |0               |https://www.virustotal.com/en/ip-address/204.132.81.133/information/ |FALSE                 |FALSE                         |0           |0               |self-signed                           |https://www.shodan.io/host/204.132.81.133 |https://www.threatcrowd.org/ip.php?ip=204.132.81.133 |0                           |0                                |0                               |https://otx.alienvault.com/indicator/ip/204.132.81.133 |http://whois.domaintools.com/204.132.81.133 |517                 |

<br>
[Back to Top][]

# Data Analytics

## Anomaly Detection

The open ports for each IP listed by Shodan were processed through R to find if any had outlying ports. This provides two pieces of intelligence: first, it shows the common ports used by others in the industry, giving an idea of what technology is commonly used; and second, it shows us those IP addresses that do not have a common port configuration, which could hint at the necessity of performing an in-depth review on those addresses. Each IP was associated with each of its open ports in a 1:1 format, and then ran through the anomalize() function in R to produce outlying open ports.

<br>
[Back to Top][]

## IP Reputation

IP Reputation analysis was performed through AlienVault OTX and Virus Total. Understanding the common malicious IP addresses is a great first step to avoid the already well-known sources of attacks companies can face. HostIntel was used to feed each IP address through both services, and the results were examined for any with a negative reputation. Alternative methods would be to gather a list of IP addresses that attempt to communicate with a network, and run that list through HostIntel / OTX / VirusTotal to get a daily view of any potential attacks.

<br>
[Back to Top][]

## Shodan Tag Correlation

Analyze Shodan Tags to search for links between bad reputation IP’s and those picked up in Anomaly Detection. Provides another avenue to investigate IP addresses with based on their tag in Shodan. Run correlation tests on IP address, Shodan Tag, and reputation information from OTX / VirusTotal. R was used to see if there is any correlation between irreputable IP addresses and their Shodan Tags.

<br>
[Back to Top][]

## Key Insights

The analytics performed give us a few useful insights:

* Understanding of ports, both common and those potentially used for malicious attacks
* Comprehensive view of reputable and irreputable IP addresses
* Ability to identify malicious IP addresses based on Shodan Tags

IP location data can be viewed over time to see if there are trends in movement in the industry, and/or ability to block potentially malicious IP addresses based on common locations.

# Visual Aids

## Censys Port Cloud

![image](https://user-images.githubusercontent.com/84549135/123334512-14bf6e80-d4f8-11eb-9cba-8d048e53efd4.png)

Shows common ports / protocols used by Censys IP results.

<br>
[Back to Top][]

## IP Location

![image](https://user-images.githubusercontent.com/84549135/123334527-1a1cb900-d4f8-11eb-8529-fea3573ec247.png)

Provides a geo-spatial overview of all IP addresses from Censys results

<br>
[Back to Top][]

## About Me

Dylan Todd is a student at the University of Arizona. He has an M.S. degree in Management Information Systems, and is currently working on his M.S. in Cybersecurity. He is the sole contributor to this project. Please send any comments or feedback to dylantodd@arizona.edu.

<br>
[Back to Top][]

Page last updated: 7:01 PM MST on 06/07/2021

[Back to top]: #table-of-contents
