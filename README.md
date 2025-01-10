# Instagram Post Automation using Make.com

## Overview
This project automates Instagram post creation using an RSS feed, a text parser, and the Instagram for Business API through Make.com. The workflow fetches content from an RSS feed, processes it into plain text, and posts it as an image caption on Instagram.

## Workflow Components

1. **RSS Trigger**
   - Module: `rss:TriggerNewArticle`
   - Fetches new articles from the specified RSS feed.
   - Parameters:
     - URL: `https://rss.app/feeds/rV9fjzrPznmC1oM6.xml`
     - Maximum Results: `1`
     - Request Compressed Content: `True`

2. **HTML to Text Parser**
   - Module: `regexp:HTMLToText`
   - Converts HTML content from the RSS feed into plain text for the Instagram caption.
   - Parameters:
     - Line Break: `LF (\n)`
     - Uppercase Headings: `True`

3. **Instagram Post Creation**
   - Module: `instagram-business:CreatePostPhoto`
   - Posts a photo to Instagram with the parsed caption.
   - Parameters:
     - Account ID: `17841455890979475`
     - Image URL: `https://i.imgur.com/zDtwsfE.jpeg`
     - Caption: Derived from parsed text.

## Prerequisites
- A Make.com account.
- Access to the RSS feed (`https://rss.app/feeds/rV9fjzrPznmC1oM6.xml`).
- An Instagram for Business account connected to a Facebook page.
- A valid Facebook connection in Make.com.

## Setup Instructions

1. **Configure the RSS Trigger**
   - Add the `rss:TriggerNewArticle` module.
   - Set the RSS feed URL and parameters.

2. **Add the HTML to Text Parser**
   - Insert the `regexp:HTMLToText` module.
   - Map the RSS article title or description to the `html` parameter.

3. **Set up the Instagram Post Module**
   - Add the `instagram-business:CreatePostPhoto` module.
   - Authenticate with your Facebook connection.
   - Configure the `accountId`, `image_url`, and `caption` parameters.

4. **Test the Workflow**
   - Run the scenario to ensure everything functions correctly.
   - Verify that the Instagram post is created as expected.

## Features
- **Dynamic Content**: Automatically pulls content from an RSS feed.
- **Customizable Captions**: Converts HTML to plain text with formatted headings.
- **Effortless Posting**: Integrates directly with Instagram for Business.

## Limitations
- The workflow assumes the RSS feed provides well-structured content.
- Instagram API limitations apply (e.g., rate limits, content policies).
- Image URL is static unless dynamically updated in the workflow.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing
Contributions are welcome! Please submit issues or pull requests to improve the workflow or documentation.

## Contact
For questions or support, feel free to reach out via [Make.com support](https://www.make.com/en/contact) or open an issue in this repository.

