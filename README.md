# onemoretry
# Import the Metaphor class from the metaphor_python package
from metaphor_python import Metaphor

# Replace 'YOUR_API_KEY' with your actual Metaphor API key
api_key = 'c5965b9f-0024-4436-b438-8a6ce8da5452'

# Create a Metaphor instance with your API key
metaphor = Metaphor(api_key)

# Define your search query for product design roles by startups
query = "hiring product designers"

# Set the minimum crawl date to filter results after September 30th, 2023
start_crawl_date = "2023-09-30T00:00:00Z"

# Additional search options (if needed)
# num_results, include_domains, etc.

# Perform the search
search_response = metaphor.search(
    query=query,
    start_crawl_date=start_crawl_date,
    type="neural"  # You can choose 'neural' for high-quality content
)

# Get the search results
results = search_response.results

# Print the results
for result in results:
    print(f"Title: {result.title}")
    print(f"URL: {result.url}")
    print(f"Published Date: {result.published_date}")
    print("----------")

# Optionally, you can also access the autoprompt string
autoprompt_string = search_response.autoprompt_string
if autoprompt_string:
    print(f"Autoprompt String: {autoprompt_string}")
