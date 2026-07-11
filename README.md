# Facebook Marketplace Scraper

The most powerful and data-rich **Facebook Marketplace Scraper** on Apify. Extracts **40+ fields** per listing — including seller intelligence, complete item details, comprehensive vehicle specs, and HD images — for **any category**. 

No login required. Built-in residential proxy routing. Pay only for successful results.

---

## 🚀 NEW: Deep Category Sweeping & Custom Filters

We've massively upgraded the scraper's intelligence. Simply searching for "Vehicles" on Marketplace usually caps out at 1,000 results. **Not anymore.**

- **Deep Subcategory Sweeping:** If you search for a broad category like "Vehicles" or "Electronics", our scraper automatically maps it to hundreds of hidden subcategories (e.g., `audi-rs5`, `acura-legend`, `mobile-phones`). It iterates through each one individually, allowing you to bypass Facebook's pagination limits and extract *tens of thousands* of listings in a single run.
- **Copy-Paste URL Intelligence:** You can now paste raw Facebook Marketplace URLs directly into the `start_urls` input! 
  - Paste an **Item URL** (or just the ID) to scrape a specific listing.
  - Paste a **Category URL** to deep-scrape that specific category.
  - Paste a **Search URL with custom filters** (like `make`, `model`, `exact=false`) and the scraper will seamlessly pass your exact filters to the scraping engine!
- **Advanced Sorting:** Force the engine to sort by **Lowest Price**, **Nearest First**, or **Newest First**. Sorting by Lowest Price combined with our Deep Category Sweeping guarantees you get the most exhaustive and accurate datasets possible without hitting pagination ceilings.

---

## Facebook Marketplace Scraper Features

When scraping Facebook Marketplace, you need reliability and deep data. Our scraper is enterprise-grade, designed to bypass Facebook's strict bot protections automatically using advanced residential proxies, ensuring you get exactly the data you need without the headache of managing proxies or accounts.

### Key Benefits:
- **🔒 No Login Required:** Scrape anonymously without risking your personal Facebook account.
- **⚡ Built-in Residential Proxies:** We handle the complex proxy routing and IP rotation. Our system automatically uses premium residential proxies to bypass blocks. **You do not need to buy your own proxies!**
- **🆓 Risk-Free Trial:** Test the scraper instantly! Free users can use the trial allowance to scrape real listings using our premium proxies. 
- **💰 Pay-Per-Result:** You only pay for successful listings extracted. Zero hidden fees.
- **🏎️ Blazing Fast:** Concurrent processing allows you to scrape up to 10x faster than sequential scrapers.

---

## 🎯 Use Cases

Whether you are a data analyst, dropshipper, or car dealership, this scraper provides the raw intelligence you need:
- **🚗 Car Dealerships & Flippers:** Extract VINs, mileage, transmission types, and body styles to find underpriced vehicles before anyone else.
- **🏠 Real Estate Agents:** Scrape rental listings, property prices, and location data to analyze local housing markets.
- **📦 Dropshippers & Resellers:** Monitor prices, discover trending electronics or furniture, and identify top-rated sellers.
- **📊 Market Researchers:** Analyze pricing trends, seller sentiment, and regional availability across the US, UK, Canada, and beyond.

---

## 📊 What data does it extract?

This scraper adapts to the category you are searching. It extracts generic fields for items like furniture, and automatically enriches vehicle listings with deep automotive specs.

### General Listing Output (Furniture, Electronics, Real Estate)
```json
{
  "url": "https://www.facebook.com/marketplace/item/123456789/",
  "title": "IKEA Malm Dresser - Like New",
  "price": "$150",
  "city_slug": "sanfrancisco",
  "seller_name": "Sarah M.",
  "seller_join_year": "Joined Facebook in 2015",
  "seller_location": "San Francisco, CA",
  "seller_rating": 4.8,
  "seller_review_count": 12,
  "pseudo_seller_id": "anon_a3f2b1c9d8e7f6a5",
  "listing_age": "12 hours ago",
  "category": "Home & Garden",
  "description": "Selling my IKEA Malm 6-drawer dresser...",
  "condition": "PC_USED_LIKE_NEW",
  "brand": "IKEA",
  "images": ["https://scontent...jpg", "..."],
  "attributes": ["White", "6 drawers"]
}
```

### Automotive/Vehicle Output (Auto-Enriched)
```json
{
  "url": "https://www.facebook.com/marketplace/item/982185697762732/",
  "title": "2019 Honda Civic EX",
  "price": "$8,500",
  "city_slug": "sanfrancisco",
  "seller_name": "Lawrence",
  "seller_rating": 4.6,
  "make": "Honda",
  "model": "Civic",
  "trim": "EX",
  "year": 2019,
  "mileage": "45000",
  "transmission": "AUTOMATIC",
  "fuel_type": "GASOLINE",
  "vin": "2HGFC2F5XKH...",
  "title_status": "CLEAN",
  "engine": "1.5L Turbo",
  "drivetrain": "FWD",
  "images": ["https://scontent...jpg"]
}
```

---

## 📥 Input Parameters

The scraper is incredibly easy to configure. Simply provide your search term and location, and let the scraper do the rest!

| Parameter | Type | Default | Description |
|---|---|---|---|
| `start_urls` | array | `[]` | **NEW!** Paste any Facebook Marketplace search, category, or item URL directly here to preserve your exact custom filters. |
| `search_query` | string | `"vehicles"` | What to search for (e.g. 'iphone', 'honda', 'desk'). |
| `city_slug` | string | `"sanfrancisco"` | Facebook city identifier (e.g. london, newyork, chicago). |
| `sort_by` | string | `"best_match"` | Sort by: Best Match, Lowest Price, Nearest First, or Newest First. |
| `min_price` | int | `1000` | Minimum price filter ($) |
| `max_price` | int | `10000` | Maximum price filter ($) |
| `price_chunk_size` | int | `50` | The dollar increment to sweep by. If searching for very cheap items (like clothes), set this to $2 or $5 to ensure no items are missed in dense price brackets! |
| `max_results` | int | `100` | Maximum listings to scrape |
| `concurrency` | int | `5` | Parallel scraping threads (1-10) for maximum speed. |
| `days_since_listed` | int | `1` | Recency filter (1 = last 24h, 7 = last week). |

---

## ❓ FAQ

**Q: Do I need to buy my own residential proxies?**  
A: **No!** Because this Actor uses Pay-Per-Result pricing, it automatically uses our premium residential proxies behind the scenes. You simply pay for the successful results you receive.

**Q: Do I need a Facebook account?**  
A: No. The scraper operates completely anonymously without any login or authentication required.

**Q: How do I bypass Facebook's 1,000 result limit?**  
A: Use our Deep Category Sweeping! Enter a broad query like `Vehicles` and the scraper will automatically break it down into hundreds of micro-searches for every individual subcategory (Audi, BMW, Ford, etc.), allowing you to extract exhaustive datasets. To prevent getting locked out, pair this with `Lowest Price` sorting.

**Q: Can I test it for free?**  
A: Yes! Free users can use the platform's free allowance to test the scraper. Because we route the proxy for you, your free test will actually work and return real data!

**Q: How fast is it?**  
A: With concurrency set to 5, expect ~100 listings in 3-5 minutes.

**Q: How do I scrape Facebook Marketplace?**
A: You can easily scrape Facebook Marketplace using this Apify Actor. Just provide the search query (e.g. "iPhone" or "Honda") and the city slug (e.g. "sanfrancisco"), and the scraper will automatically navigate the site, bypass protections using residential proxies, and return the listings in JSON or CSV format.

**Q: Is it legal to scrape Facebook Marketplace?**
A: Scraping publicly available data is generally considered legal, but you should always review Apify's ethical guidelines and Facebook's terms of service. This scraper only extracts public data that any user would see when browsing Marketplace.

**Q: Can you scrape Facebook Marketplace for cars and real estate?**
A: Yes! This Facebook Marketplace scraper is specially optimized for vehicles and real estate. For cars, it automatically extracts VINs, mileage, transmission, and more. For real estate, it captures rental prices and locations.

---

*Keywords: Facebook Marketplace scraper, Facebook data extraction, FB Marketplace API, scrape Facebook cars, real estate scraper, dropshipping product research, lead generation.*
