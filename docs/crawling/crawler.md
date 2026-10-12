# askFinzBot · The askFinz search crawler

askFinzBot reads public pages for the askFinz search index. It follows robots.txt, keeps a slow pace, signs every request so you can verify it, and never uses your pages for AI training.

**Canonical page:** [https://askfinz.com/crawler](https://askfinz.com/crawler)

## Key points

### What askFinzBot looks like in your logs

Every request carries this User-Agent, and it never changes from one request to the next:

### Four rules it never breaks

Reads robots.txt first, and obeys it Before it asks for any page it reads your robots.txt and follows the rules written for askFinzBot, or for everyone if there are none. If your robots.txt cannot be reached because your server is having trouble, it does not crawl at all.

### Blocking or limiting askFinzBot

Add a group to your robots.txt. askFinzBot reads it again at least every hour, so a change takes effect within the hour.

### Signed requests you can check

askFinzBot signs every request using Web Bot Auth, an open standard built on HTTP Message Signatures. Each request carries three headers: Signature-Agent, Signature-Input and Signature.

### askFinz-Crawler and the rest of the family

Besides askFinzBot, parts of askFinz read the web under their own names. Everything below is about those readers, not about askFinzBot.

### What it looks like from your side

A crawl opens with robots.txt, picks up your sitemap if you publish one, and then works through pages at a steady, spaced pace. Requests carry this User-Agent:

### Allowing askFinz-Crawler

You don't need to do anything for us to read a public page. These are for the case where something in front of your site is turning us away.

### One name, a few purposes

Different parts of askFinz read the web for different reasons, and each says which it is. That way you can allow one and refuse another instead of making a single all-or-nothing decision.

### How it behaves on your site

Follows robots.txt When it crawls your site it reads your robots.txt first and follows your rules — including Crawl-delay, which it will only ever wait longer than, never shorter.

### Checking it's really us

Our requests reach sites through a privacy layer with rotating exits, so askFinz-Crawler does not come from one fixed IP address. Verify by the User-Agent token above rather than by address.

## Frequently asked

### What is askFinzBot for?

It reads public pages so they can be found through askFinz search. When an answer draws on your page, it names your page and links to it.

### Is my content used to train AI models?

No. Pages askFinzBot reads are marked when they are stored and are excluded from every training data set we build. They are used only to answer searches, with a link back to you.

### How do I block it?

Add a group for askFinzBot to your robots.txt with "Disallow: /". It reads robots.txt again at least every hour, so a change takes effect within the hour. You can also block just some folders.

### How do I check a request really came from you?

Every request is signed using the Web Bot Auth standard (HTTP Message Signatures). Our public key is published in our key directory, and security services that support the standard check it automatically.

### Why does askFinz-Crawler come from different IP addresses?

Its connection routes through a privacy layer with rotating exits, so there is no single fixed address to allow-list. Match on the User-Agent instead. If your setup genuinely requires IP allow-listing, contact us and we can arrange a dedicated address.

### Does being crawled cost me anything?

It shouldn't be noticeable. Requests are spaced out and rate-limited, and your Crawl-delay is always respected. If you're seeing load you can attribute to us, tell us and we'll slow down for your domain.

### Can I get my site indexed faster?

Yes — verified domain partners are read directly and refreshed with priority rather than waiting to be reached in the normal course of crawling.

### What happens to a page once you've read it?

It becomes part of the index that askFinz searches when someone asks a question. Answers drawn from your page cite it and link back to you, so the attribution stays with the source rather than being absorbed anonymously.

## Related

- [Submit a domain · the Web Index](https://askfinz.com/submit-domain)
- [Web safety · the Web Index](https://askfinz.com/web-safety)

---

Summary of [https://askfinz.com/crawler](https://askfinz.com/crawler), generated from the page itself. The page is the source of truth. Contact: hello@askfinz.com
