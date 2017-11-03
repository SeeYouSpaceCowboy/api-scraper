<p align="center">
  <img
    src="https://user-images.githubusercontent.com/7621982/32139395-10478d60-bc15-11e7-8608-3be6ccd96a1e.png"
    alt="terminal"
    width="30" />
</p>
<h3 align="center">
  Scraper
</h3>
<p align="center" style="color: #999;">Web Scraper API</p>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/7621982/32139413-fa7fcc94-bc15-11e7-93b1-0ad8648a8c4f.png"
    alt="Scraper Screenshot"
    width="700" />
    <br>
    Scrape any website's H1, H2, H3 and link tags.
</p>

## Getting Started with Scraper
These instructions will get you a copy of the project up and running on your local machine for development.

### Prerequisites
Things you need to install beforehand:
* **Rails** - Ruby Framework

### Installing
Open terminal and run the following lines of code to clone and run this project.

 ```shell
 $ git clone https://github.com/SeeYouSpaceCowboy/api-scraper.git
 $ cd api-scraper
 $ bundle install
 $ rails s
 ```
 This project should now be running locally on port `3000`.

# About
These instructions are a small documentation of the how the API should behave.

Example calls are made using JavaScript's `axios` npm package.

### Scrape Given URL

Saves H1, H2, H3 and links from a given URL to the database.

| URL Endpoint | Method | URL Params | Success Response |
| ----- | ----- | ----- | ----- |
| `/url` | `POST` | Required: `link=[string]` | `200` |

**Sample Call:**

  ```javascript
    axios.post('http://localhost:3000/api/v1/urls', { link: 'http://dailynews.com' })
      .then(response => response)
  ```

### Get All H1, H2, H3 and Links

  Get back H1, H2, H3 and links from a previously saved URLs from the database.

  | URL Endpoint | Method | URL Params | Success Response |
  | ----- | ----- | ----- | ----- |
  | `/url` | `GET` | N/A | `200` |

  **Sample Call:**

  ```javascript
    axios.get('http://localhost:3000/api/v1/urls')
      .then(response => response)
  ```

  **Content:**
  ```
  [
    {
      "link": "http://dailynews.com",
      "h1": [
        {
            "content": "Passenger dies after car crash in North Hollywood",
            "link": "http://www.dailynews.com/2017/10/27/1-in-critical-condition-after-car-crash-in-north-hollywood/"
        },
        ...
      ],
      "h2": [
        {
            "content": "LA Metro security guards attacked near Watts station; one shot at with his own gun",
            "link": "http://www.dailynews.com/2017/10/27/la-metro-security-guards-attacked-near-watts-station-one-shot-at-with-his-own-gun/"
        },
        ...
      ],
      "h3": [ ... ],
      "a": [ ... ]
    },
    ...
  ]
  ```
## Contributors
Scraper was built by [Mohammed Chisti](http://mohammedchisti.com).
