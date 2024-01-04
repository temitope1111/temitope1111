- 👋 Hi, I’m @temitope1111
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
temitope1111/temitope1111 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#import requests
#from bs4 import BeautifulSoup

#def extract_and_save_content(url, output_file):
    # Fetch the webpage content
   # response = requests.get(url)

  #  if response.status_code == 200:
        # Parse the HTML content using BeautifulSoup
  #      soup = BeautifulSoup(response.text, 'html.parser')

        # Find the main content element (you may need to inspect the HTML to find the appropriate tag)
   #     main_content = soup.find('div', {'class': 'main-content'})  # Adjust class based on the actual structure

  #      if main_content:
            # Extract content as a string
  #          content_text = main_content.get_text()

            # Save the content to a text file
  #          with open(output_file, 'w', encoding='utf-8') as file:
  #              file.write(content_text)

  #          print(f"Content saved successfully to {output_file}")
  #      else:
  #          print("Main content element not found on the webpage.")

  #  else:
   #     print(f"Failed to fetch the webpage. Status code: {response.status_code}")

# Example usage:
#ferpa_url = "https://studentprivacy.ed.gov/ferpa"
#output_file = "ferpa_content.txt"
#extract_and_save_content(ferpa_url, output_file)


#https://studentprivacy.ed.gov/content/ppra

import requests
from bs4 import BeautifulSoup

def extract_and_save_content(url, output_file):
    # Fetch the webpage content
    response = requests.get(url)

    if response.status_code == 200:
        # Parse the HTML content using BeautifulSoup
        soup = BeautifulSoup(response.text, 'html.parser')

        # Find the main content element (you may need to inspect the HTML to find the appropriate tag)
        main_content = soup.find('div', {'class': 'main-content'})  # Adjust class based on the actual structure

        if main_content:
            # Extract content as a string
            content_text = main_content.get_text()

            # Save the content to a text file
            with open(output_file, 'w', encoding='utf-8') as file:
                file.write(content_text)

            print(f"Content saved successfully to {output_file}")
        else:
            print("Main content element not found on the webpage.")

    else:
        print(f"Failed to fetch the webpage. Status code: {response.status_code}")

# Example usage:
ppra_url = "https://studentprivacy.ed.gov/content/ppra"
output_file = "ppra_content.txt"
extract_and_save_content(ppra_url, output_file)
