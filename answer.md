Task 1 — PII Classification & Data Handling

1.full_name
PII TYPE- Direct PII,
Action-  drop it, pseudonymize it,
Reason- is a direct identifer not need for external research

2.email
PII TYPE- Direct PII,
Action- drop it,
Reason- is a uniquely identify the person

3.date_of_birth
PII TYPE- Direct PII,
Action- mask it,
Reason- DOB exactly can identify by indivduals

4.zip_code
PII TYPE- Indirect PII,
Action- generalize,
Reason- Small ZIP areas can identify people

5.job_title
PII TYPE- Indirect PII,
Action- Keep but categorize,
Reason- Rare job titles can identify people; convert into broad categories.

6. diagnosis_notes
PII Type- may include hidden PII,
Action- Retain but scrub for names, emails, phone numbers,
Reason- Needed for research; must remove embedded identifiers.


Task 2 — Audit the API Script for Ethical Compliance

Issue 1 — Using a Free-tier API key for large-scale data collection

import os
import requests

API_URL = "https://healthstats-api.example.com/records"
API_KEY = "free_tier_key_abc123"  # use a secure authenticated key

response = requests.get(
    API_URL,
    params={"page": page},
    headers={"Authorization": f"Bearer {API_KEY}"}
    
)

Issue 2 — Saving raw patient data permanently

The script stores raw health records without cleaning or anonymizing them.
This is not ethical and may violate privacy laws.

# process or anonymize before storing
clean_records = anonymize(records)

# only store the cleaned version
save_to_database(clean_records)
