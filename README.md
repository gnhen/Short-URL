# Short-URL
Open source short URL maker

## Usage

### [http://gshort.site](http://gshort.site)

Visit [https://gshort.site](https://gshort.site) to use the URL shortener. Enter a long URL in the input field and click the "Shorten" button. After a few minutes, the shortened URL will be available.

## Forking and Using This Repo

To fork this repository and use it for yourself:

1. Fork the repository on GitHub.
2. Clone the forked repository to your local machine.
3. Update the `CNAME` file with your custom domain (if you have one).
4. Update the `BASE_URL` and `TOKEN` constants in `index.html` with your GitHub repository details and a personal access token.
5. Update the API call where this comment is located: ```Update "USERNAME" and "REPOSITORY" respectively```
6. Enable GitHub Pages for your repository.
7. Push your changes to the `main` branch.

## How It Works

This project is a proof of concept for a URL shortener that uses GitHub Actions to create short versions of URLs. The main components are:

1. **index.html**: The main web page where users can enter a URL to shorten. It includes a form to input the long URL and a button to generate the short URL. The page also handles redirection based on the short URL code.
2. **data/urls.js**: A JavaScript file that stores the mappings between short URLs and long URLs.
3. **.github/workflows/update-url-mappings.yml**: A GitHub Actions workflow that processes new URL entries from GitHub issues and updates `data/urls.js` with the new mappings.

### Code Explanation

- **index.html**: Contains the HTML structure and JavaScript code to handle URL shortening and redirection. The `shortenURL` function sends a request to create a new GitHub issue with the long URL and the generated short code. The `handleRedirect` function checks if a short code is present in the URL query parameters and redirects to the corresponding long URL if found.
- **data/urls.js**: Stores the URL mappings in a JavaScript object format.
- **.github/workflows/update-url-mappings.yml**: Defines a GitHub Actions workflow that triggers when a new issue is opened. It extracts the short and long URLs from the issue body, updates `data/urls.js`, and commits the changes back to the repository.


### License

This work is licensed under a Creative Commons Attribution-NonCommercial 4.0 International License. You are free to use and copy this work, but not for commercial purposes.

&copy; 2024 Grant Hendricks.
