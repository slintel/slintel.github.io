---
title: Enrich Lead on email
position_number: 1.3
type: get
description: This endpoint enriches a lead’s information based on the value found in the email field.
content_markdown: |-
  The lead enrichment endpoint consumes credits for its usage. If a verified email is successfully returned, it will 
  cost you 1 credit. If an email/phone is not found, but Slintel successfully found ALL of the following information, 
  Slintel will charge a fraction of a credit.
  
  The lead enrichment endpoint also charges credits if you pass the same information multiple times.
  {: .warning }
left_code_blocks:
  - code_block: |-
        var request = require('request');
        var options = {
          'method': 'GET',
          'url': 'https://apiv2.slintel.com/v2.0/lead/enrich?email=deepak@slintel.com',
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
            "url": "https://apiv2.slintel.com/v2.0/lead/enrich?email=deepak@slintel.com",
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

        url = "https://apiv2.slintel.com/v2.0/lead/enrich?email=deepak@slintel.com"
        
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
        "id": "5dc164616d4235090c39736b",
        "continent": "North America",
        "country": "United States",
        "education": [
        {
            "end_date": 2008,
            "school_location": "Indore, Madhya Pradesh, India",
            "school_website": "iimidr.ac.in",
            "school_name": "Indian Institute Of Management Indore",
            "degrees": [
                "Master Of Business Administration",
                "Masters"
            ],
            "start_date": 2006
        },
        {
            "end_date": 2006,
            "school_location": "Kharagpur, West Bengal, India",
            "school_website": "iitkgp.ac.in",
            "school_name": "Indian Institute Of Technology Kharagpur",
            "degrees": [
                "Bachelors"
            ],
            "start_date": 2002
        }
        ],
        "decision_making_power": "High",
        "city": "San Francisco",
        "company_website": "slintel.com",
        "experience": [
        {
            "end_date": [],
            "is_primary": "true",
            "company_profile": {},
            "company_website": "slintel.com",
            "company_name": "Slintel",
            "location": {
                "country": "United States",
                "city": "Mountain View",
                "state": "California"
            },
            "title_name": "Founder",
            "company_size": "1-10"
        },
        {
            "is_primary": "false",
            "company_profile": {
                "facebook_url": "facebook.com/tracxn",
                "twitter_url": "twitter.com/tracxn",
                "crunchbase_url": "crunchbase.com/organization/tracxn"
            },
            "company_website": "tracxn.com",
            "company_name": "Tracxn",
            "location": {
                "country": "United States",
                "city": "Palo Alto",
                "state": "California"
            },
            "title_name": "Vp, Business Development",
            "company_size": "501-1000"
        }
        ],
        "technologies": [
        {
            "category": "Finance and Accounting",
            "subcategory": "Billing And Provisioning",
            "technology": "Square Invoices",
            "last_detected": 1589915623
        },
        {
            "category": "Platform and Storage",
            "subcategory": "Backup and Disaster Recovery",
            "technology": "Rewind.io",
            "last_detected": 1591092110
        }
        ],
        "company_linkedin_url": "https://www.linkedin.com/company/slintel/",
        "skills": [
        "Business Strategy",
        "Portfolio Management",
        "Financial Modeling",
        "Management",
        "Banking",
        "Consulting",
        "Business Development",
        "Requirements Analysis",
        "Business Analytics",
        "Investments",
        "Business Analysis",
        "Team Management",
        "Pre Sales",
        "Business Intelligence",
        "Strategy",
        "Financial Services",
        "Sales",
        "Management Consulting"
        ],
        "company_state": "California",
        "function": "Ceo/founder/co-founder",
        "company_city": "Santa Clara",
        "state": "California",
        "email": "deepak@slintel.com",
        "divison": "General",
        "company_id": "5c3b016dd55ae49f1b77d266",
        "lead_title": "Founder",
        "company_country": "United States",
        "company_products_services": [
        "Information and Communications Technology (ICT)",
        "Information Technology",
        "Marketing Automation",
        "Sales Automation"
        ],
        "company_phone_number": "214-400-7300",
        "industry": "Computer Software",
        "company_sector": "Technology",
        "company_name": "Slintel",
        "company_twitter_url": "https://twitter.com/slintel_inc",
        "name": "Deepak Anchala",
        "company_facebook_url": "https://www.facebook.com/Slintel-1070643269715139/",
        "linkedin_url": "http://www.linkedin.com/in/deepak-anchala-0043707",
        "company_size": "11-50",
        "last_funded_on": 1576108800
        }
        }
    title: Response
    language: json
---