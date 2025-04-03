
```python
from googlesearch import search

def find_company_website(company_name):
    query = f"{company_name} official website"
    results = list(search(query, num_results=1))  # Get first search result
    return results[0] if results else "Website not found"

company = "FINE SURFACES AND MORE"
website = find_company_website(company)
print(f"Website for {company}: {website}")

```

    Website for TCS: https://www.tcs.com/
    
