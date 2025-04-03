```python
!pip install wikipedia
```

    Collecting wikipedia
      Downloading wikipedia-1.4.0.tar.gz (27 kB)
      Installing build dependencies: started
      Installing build dependencies: finished with status 'done'
      Getting requirements to build wheel: started
      Getting requirements to build wheel: finished with status 'done'
      Preparing metadata (pyproject.toml): started
      Preparing metadata (pyproject.toml): finished with status 'done'
    Requirement already satisfied: beautifulsoup4 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from wikipedia) (4.12.2)
    Requirement already satisfied: requests<3.0.0,>=2.0.0 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from wikipedia) (2.31.0)
    Requirement already satisfied: charset-normalizer<4,>=2 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (3.1.0)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (2.10)
    Requirement already satisfied: urllib3<3,>=1.21.1 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (2.0.3)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (2023.5.7)
    Requirement already satisfied: soupsieve>1.2 in c:\users\hp\appdata\local\programs\python\python311\lib\site-packages (from beautifulsoup4->wikipedia) (2.4.1)
    Building wheels for collected packages: wikipedia
      Building wheel for wikipedia (pyproject.toml): started
      Building wheel for wikipedia (pyproject.toml): finished with status 'done'
      Created wheel for wikipedia: filename=wikipedia-1.4.0-py3-none-any.whl size=11787 sha256=be55d0bd71d95258913040dcc26f8259201e18359f85e6295990fc5e871d5108
      Stored in directory: c:\users\hp\appdata\local\pip\cache\wheels\8f\ab\cb\45ccc40522d3a1c41e1d2ad53b8f33a62f394011ec38cd71c6
    Successfully built wikipedia
    Installing collected packages: wikipedia
    Successfully installed wikipedia-1.4.0
    


```python
import wikipediaapi

def find_company_website(company_name):
    user_agent = "MyPythonApp/1.0 (contact@example.com)"  
    wiki = wikipediaapi.Wikipedia(user_agent=user_agent, language="en")
    page = wiki.page(company_name)

    if page.exists():
        return page.fullurl
    return "Website not found"

company = "Tesla"
website = find_company_website(company)
print(f"Website for {company}: {website}")

```

    Website for Tesla: https://en.wikipedia.org/wiki/Tesla
    


```python
from googlesearch import search

def find_company_website(company_name):
    query = f"{company_name} official website"
    results = list(search(query, num_results=1))  # Get first search result
    return results[0] if results else "Website not found"

company = "TCS"
website = find_company_website(company)
print(f"Website for {company}: {website}")

```

    Website for TCS: https://www.tcs.com/
    
