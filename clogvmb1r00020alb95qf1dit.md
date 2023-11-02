---
title: "The Shortest Guide To Web Scraping With Apify"
seoTitle: "The Shortest Guide To Web Scraping With Apify"
datePublished: Thu Nov 02 2023 07:39:49 GMT+0000 (Coordinated Universal Time)
cuid: clogvmb1r00020alb95qf1dit
slug: the-shortest-guide-to-web-scraping-with-apify
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1698909731617/89e1e41a-e006-491f-817a-4a7fc64236c4.png
tags: python, web-development, apis, web-scraping, apify

---

In this article, you'll learn the basics of web scraping and how to get your journey into web scraping started. This article contains all the basic concepts of web scraping and could serve as a guide to getting you into web scraping with Apify.

## What is Web Scraping?

Web scraping is a technique used for extracting data and content from web pages, mostly by using bots. Web scraping could extract all the data or selected data; it all depends on who is scraping the data. Usually, when all the data needed is scraped, it's exported as a spreadsheet or an API. These bots have a way of working: they first make HTTP requests, then do some HTML parsing and lastly, they extract data. These are the three main things they execute.

There are different ways you could get your journey into web scraping started. Using web scraping APIs, libraries, and tools could get you into web scraping. Using these methods will make web scraping very efficient for you.

## Basics of Web Scraping

* **HTTPS Requests**: When the bot gets the web page, it uses a **GET** request to fetch data from the web page. Note that not all websites will allow you to scrape their data. The response you get from the request is what gives you access to scrape data.
    
* **Data Extraction from HTML Code**: After getting the response from the HTTP request, your data can now be extracted from the HTML code. You may also need to do some HTML parsing when you eventually have your HTML content - this can be best done with parsing libraries like Beautiful Soup, xlml, or even pyquery.
    
* **Data Storage**: After extracting all the unstructured data, you have to sort it so it can be used properly. Structuring and storing data could be done in two ways: in a CSV or JSON file. This makes the data suitable for use. Alternatively, you could store your scraped data using cloud storage infrastructures like AWS S3, Google Cloud, or even Fermyon Cloud.
    

## Navigating your Web Scraping with Apify

Web scraping has been very easy to do with platforms like Apify. Apify is a platform for building, deploying, and even monitoring your web scrapers and data extraction tools. With Apify, you can build bots that could help you scrape data from web pages. In this short guide, you will learn how to use Apify to extract data using a web scraper from Apify. Apify has a lot of scrapers it provides to every one of its users, so I won't be building one from scratch; I'll be using a web scraper to extract data.

* **Create an Apify account**: Before anything, you need to [create an Apify account](https://console.apify.com/sign-up). This is just the first thing to do. Getting an account with Apify is free but you can choose to upgrade your plan later on.
    
* **Navigating through your Dashboard**: After creating your Apify account, your journey gets started. Now you can see a dashboard with quite a lot of web automation tools - over 1000. You can use anyone, depending on the type of data you're trying to scrape.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698312931430/fd13049e-c162-4aea-8bd7-6b3ec543ef45.png align="center")
    
* **Using the 'Web Scraper' actor**: Since this article won't be too technical, we will be using the **Web Scraper** actor. What this actor does is load URLs in your browser and execute a page function to extract data from the website you're extracting data from. This lets your data get extracted and exported in the format you want.
    
    On the input tab of the Web Scraper actor, you will find a panel for Basic Configuration. Now, all you have to do is change your start URL and Glob patterns to the URL you want to extract data from. In this case, we will be using Twitter's About webpage. You can see what it looks like in this image:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698317239318/7370aa15-f7bd-4506-aa48-9b070cbc29ba.png align="center")
    
    After doing this, click the Save and Run button on the dashboard. It should take you to the logs panel, where you can see how the data is being extracted. To export the data into a structured format, you can navigate to the storage panel. You can choose to save your data as a CSV file, an XML file, a JSON file, or a few other formats. And that gets you into your web scraping journey.
    

## Conclusion

This may be the easiest way for most people to get into web scraping. It isn't too technical because this is just a short guide on how you can get things started in web scraping. There are so many technical things to talk about in Apify but this article is an introductory one. I hope you enjoyed reading it and I hope this helps someone out there. I can't wait to have you read my next article!