---
title: Enrich Company
position_number: 1.1
type: get
description: This endpoint enriches company insights based on the value in the company name and/or company domain fields.
parameters:
  - name: company_name
    content: name of the company
  - name: company_website
    content: domain of the company
content_markdown: |-
  Returns a matched company from Slintel database.
left_code_blocks:
  - code_block: |-
        var request = require('request');
        var options = {
          'method': 'GET',
          'url': 'https://apiv2.slintel.com/v2.0/company/enrich?company_website=aliaxis.com',
          'headers': {
            'x-api-key': 'YOUR API KEY'
          }
        };
        request(options, function (error, response) { 
          if (error) throw new Error(error);
          console.log(response.body);
        });
    title: Nodejs
    language: javascript
  - code_block: |-
        var settings = {
            "url": "https://apiv2.slintel.com/v2.0/company/enrich?company_website=aliaxis.com",
            "method": "GET",
            "timeout": 0,
            "headers": {
            "x-api-key": "YOUR API KEY"
            },
        };
        $.ajax(settings).done(function (response) {
            console.log(response);
        });
    title: jQuery
    language: javascript
  - code_block: |-
        import requests

        url = "https://apiv2.slintel.com/v2.0/company/enrich?company_website=aliaxis.com"
        
        payload  = {}
        headers = {
          'x-api-key': 'YOUR API KEY'
        }
        
        response = requests.request("GET", url, headers=headers, data = payload)
        
        print(response.text.encode('utf8'))
    title: Python
    language: python
right_code_blocks:
  - code_block: |2-
        {
            "data": {
            "id": "5c3b016dd55ae49f1b77d266",
            "company_website": "slintel.com",
            "company_country": "United States",
            "company_products_services": [
            "Information and Communications Technology (ICT)",
            "Information Technology",
            "Marketing Automation",
            "Sales Automation"
            ],
            "technologies": [
                {
                    "category": "Others",
                    "subcategory": "Keywords",
                    "technology": "Satisfaction",
                    "last_detected": 1591092110
                },
                {
                    "category": "Platform and Storage",
                    "subcategory": "Backup and Disaster Recovery",
                    "technology": "Rewind.io",
                    "last_detected": 1591092110
                }
            ],
            "company_linkedin_url": "https://www.linkedin.com/company/slintel/",
            "industry": "Computer Software",
            "company_state": "California",
            "company_sector": "Technology",
            "company_name": "Slintel",
            "company_twitter_url": "https://twitter.com/slintel_inc",
            "company_city": "Santa Clara",
            "company_phone_number": "214-400-7300",
            "company_facebook_url": "https://www.facebook.com/Slintel-1070643269715139/",
            "company_homepage_url": "https://www.slintel.com/",
            "last_funded_on": 1576108800,
            "company_size": "11-50"
            }
        }
    title: Response
    language: json
---