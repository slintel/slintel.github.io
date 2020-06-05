---
title: Search Leads
position_number: 1.2
type: get
description: This endpoint searches for lead in Slintel's Database.
parameters:
  - name: lead_titles
    content: lead_titles (eg. cxo, manager, vp)
  - name: company_websites
    content: domain of the company
  - name: location
    content: location of leads
  - name: page
    content: page number to extract the records
content_markdown: |-
  Returns a matched company from Slintel database.
  
  This call will return a maximum of 50 leads
  {: .info }
left_code_blocks:
  - code_block: |-
        var request = require('request');
        var options = {
          'method': 'POST',
          'url': 'https://apiv2.slintel.com/v2.0/lead/search',
          'headers': {
            'x-api-key': 'YOUR API KEY',
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({"payload":{"lead_titles":["cxo","vp"],"company_websites":["amazon.com"],"location":["california","united stated"]},"page":1})
        };
        request(options, function (error, response) { 
          if (error) throw new Error(error);
          console.log(response.body);
        });

    title: Nodejs
    language: javascript
  - code_block: |-
        var settings = {
          "url": "https://apiv2.slintel.com/v2.0/lead/search",
          "method": "POST",
          "timeout": 0,
          "headers": {
            "x-api-key": "YOUR API KEY",
            "Content-Type": "application/json"
          },
          "data": JSON.stringify({"payload":{"lead_titles":["cxo","vp"],"company_websites":["amazon.com"],"location":["california","united stated"]},"page":1}),
        };
        
        $.ajax(settings).done(function (response) {
          console.log(response);
        });
    title: jQuery
    language: javascript
  - code_block: |-
        import requests

        url = "https://apiv2.slintel.com/v2.0/lead/search"
        
        payload = "{\"payload\":{\"lead_titles\":[\"cxo\",\"vp\"],\"company_websites\":[\"amazon.com\"],\"location\":[\"california\",\"united stated\"]},\"page\":1}"
        headers = {
          'x-api-key': 'YOUR API KEY',
          'Content-Type': 'application/json'
        }
        
        response = requests.request("POST", url, headers=headers, data = payload)
        
        print(response.text.encode('utf8'))
    title: Python
    language: python
right_code_blocks:
  - code_block: |2-
        {
          "payload": {
            "lead_titles": [
              "cxo",
              "vp"
            ],
            "company_websites": [
              "amazon.com"
            ],
            "location": [
              "california",
              "united stated"
            ]
          },
          "page": 1
        }
    title: Request
    language: json
  - code_block: |2-
        {
            "data": [
            {
                "id": "5d525e606dd1791d7d215953",
                "country": "United States",
                "company_id": "5c3b000ad55ae49f1b75f1a3",
                "city": "Seattle",
                "lead_title": "Vp & Cto",
                "company_name": "Amazon",
                "company_website": "amazon.com",
                "name": "Werner Vogels",
                "state": "Washington"
            },
            {
                "id": "5dc13dde2038fe24d4a72dae",
                "country": "United States",
                "company_id": "5c3b000ad55ae49f1b75f1a3",
                "city": "Los Angeles",
                "lead_title": "Ceo",
                "company_name": "Amazon",
                "company_website": "amazon.com",
                "name": "Vins Loo",
                "state": "California",
                "linkedin_url": "http://www.linkedin.com/in/vins-loo-667844109"
            },
            {
                "id": "5ebb8d5da0e7595308ad1b2d",
                "country": "United States",
                "city": "Milpitas",
                "lead_title": "Vice President",
                "company_website": "amazon.com",
                "company_name": "Amazon",
                "name": "John Berklecamp",
                "state": "California",
                "linkedin_url": "http://www.linkedin.com/in/john-berklecamp-25bb6b78"
            }
        ],
        "total": 442
        }
    title: Response
    language: json
---