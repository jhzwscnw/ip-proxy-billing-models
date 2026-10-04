# proxy for account management: choosing IP-based vs GB-based plans, what 9Proxy actually charges, and the setup that keeps profiles from linking

Take a step back from the tool lists for a second and look at the actual failure mode. You have twenty marketplace seller accounts, or forty social profiles, or a handful of ad accounts. Something gets restricted. You check the obvious things, and the IPs are different. Then you find out the IPs were *different but dirty* — reused by three other people that week, already flagged by the platform's reputation layer, or rotating mid-session right when a verification email went out.

That is the real problem behind "proxy for account management." It is not about hiding. It is about giving each account one stable, clean, plausibly located IP for as long as that account's session needs it, and not paying for bandwidth you never touch. Almost every mistake in this space comes from picking the pricing model first and the workflow second.

9Proxy is a residential provider built around that choice, and it happens to bill in two completely different ways — per IP, or per gigabyte. Which one you pick changes your monthly cost more than anything else in your stack. So that's what this covers: what the two models do, what every tier costs right now, and where each one quietly stops working.

## What a residential IP actually does for account work

Platforms link accounts through a pile of signals, and IP is only one of them — but it's the one that gets checked first and logged permanently.

Datacenter proxies fail here immediately. Their ASNs are public, so Cloudflare, Akamai, and every marketplace's fraud stack recognise the range before your login request even completes. Residential IPs come from real ISP connections tied to consumer devices, so the request looks like a person on a home connection in the city you selected.

That matters in a very specific way for account management: the IP has to match the story. A profile claiming to be in Warsaw, logging in from a Warsaw residential IP, on a browser fingerprint that also says Warsaw, survives scrutiny. The same profile logging in from a Frankfurt datacenter range gets asked for documentation.

9Proxy runs 20M+ residential IPs across 90+ countries and supports HTTP/HTTPS and SOCKS5, with targeting down to country, state, city, ZIP, and ISP level. That last part — ISP targeting — is the one account managers underuse. On some platforms, an IP that resolves to a mobile carrier looks different from one attached to a residential broadband ISP, and matching the account's original creation context reduces verification prompts.

## Two billing models, two different account-management plans

This is the decision that actually determines your bill. 9Proxy sells residential access as either a fixed number of IPs with unlimited bandwidth, or a traffic balance you spend through rotating endpoints.

**Residential by IPs** — you buy a package of IPs. Each activated IP has no traffic cap. The constraint is IP lifetime: an IP stays usable for a few hours up to about 24 hours, then it goes offline naturally, which is normal residential behaviour. Unused IPs in your balance don't expire — they only count once you actually forward them. Setup requires 9Proxy's desktop app, which does local port forwarding (you get `127.0.0.1` addresses on different ports) and handles proxy authentication if you want it.

**Residential by GB** — you buy a traffic balance and generate unlimited endpoints from it. Nothing counts against you except the gigabytes you push through. Sessions are configurable as sticky or rotating, authentication is username/password or IP whitelisting, and everything runs from the dashboard with no app install. GB balances are valid for 180 days, and enterprise GB packages have no expiry at all.

For account work, the split is fairly clean:

| Your situation | Model that fits | Why |
| --- | --- | --- |
| One IP per account, long sessions, unpredictable page weight | IP-based | Unlimited traffic per IP means a heavy dashboard or a long video call doesn't eat your budget |
| Many accounts, short sessions, lots of rotation | GB-based | You pay for the few hundred megabytes each login actually uses |
| Mixed workload — some fixed sessions, some bulk rotation | Bundle | Both resources in one package, 180-day traffic validity |

The trap is assuming GB-based is always cheaper because the headline number looks smaller. A social media manager running eight heavy accounts with constant media uploads can burn through 50 GB in a month. At the 50+5 GB tier that's $105. The same workload on IP-based costs $24 for 100 IPs — and the eight IPs they need are a rounding error inside that. Conversely, someone doing light geo-checking across 400 cities would waste most of a 100-IP balance.

## Every 9Proxy plan and price

9Proxy raised prices on IP-based and bundle products on June 1, 2026 — the first adjustment in the company's history, per its own announcement. GB-based pricing stayed exactly the same, which is the detail worth remembering if you were comparing 9Proxy to another provider using an old review.

> "Starting June 1st, 2026 (00:00 UTC), 9Proxy will update pricing for our IP-Based Packages and Bundle Packages. Note: If you rely on our GB-Based Packages, nothing changes for you, those prices will remain exactly as they are."

Current pricing runs from $0.018 per IP and $0.68 per GB at the highest volumes.

**IP-based residential (unlimited bandwidth per active IP)**

| Package | Cost per IP | Total | Notes |
| --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | Smallest practical starting point \| [ check the current IP packages](https://bit.ly/9-Proxy) |
| 500 IPs | $0.144 | $72 | Solo operators, light multi-accounting \| [ view the 500 IP tier](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | $0.084 | $126 | 1,500 IPs total at this price \| [ see the bonus IP deal](https://bit.ly/9-Proxy) |
| 2,500 IPs | $0.084 | $210 | Several verticals at once \| [ compare the 2,500 IP tier](https://bit.ly/9-Proxy) |
| 5,000 IPs | $0.072 | $360 | Agencies running client portfolios \| [ view the agency-tier package](https://bit.ly/9-Proxy) |
| 15,000 IPs | $0.048 | $720 | Regional teams \| [ check high-volume IP pricing](https://bit.ly/9-Proxy) |
| 25,000 IPs | $0.035 | $863 | Heavy automation \| [ see 25,000 IP options](https://bit.ly/9-Proxy) |
| 50,000 IPs | $0.029 | $1,438 | Reseller scale \| [ open reseller-scale pricing](https://bit.ly/9-Proxy) |

**Business IP packages (industrial volume)**

| Package | Cost per IP | Total |
| --- | --- | --- |
| 100,000 IPs | $0.023 | $2,300 \| [ view business IP packages](https://bit.ly/9-Proxy) |
| 200,000 IPs | $0.021 | $4,140 \| [ compare 200,000 IP pricing](https://bit.ly/9-Proxy) |
| 500,000 IPs | $0.018 | $8,625 \| [ see top-volume IP pricing](https://bit.ly/9-Proxy) |

**GB-based residential (180-day validity, unlimited endpoints)**

| Package | Cost per GB | Total |
| --- | --- | --- |
| 5 GB | $3.00 | $15 \| [ start with a 5 GB balance](https://bit.ly/9-Proxy) |
| 50 GB + 5 bonus | $2.10 | $105 \| [ check the bonus GB package](https://bit.ly/9-Proxy) |
| 100 GB | $1.50 | $150 \| [ view the 100 GB tier](https://bit.ly/9-Proxy) |
| 200 GB | $1.00 | $200 \| [ compare the 200 GB tier](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80 | $800 \| [ see 1,000 GB pricing](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75 | $1,500 \| [ open the 2,000 GB tier](https://bit.ly/9-Proxy) |

**Enterprise GB packages (no expiry)**

| Package | Cost per GB | Total |
| --- | --- | --- |
| 3,000 GB | $0.72 | $2,160 \| [ view enterprise GB packages](https://bit.ly/9-Proxy) |
| 6,000 GB | $0.70 | $4,200 \| [ compare enterprise tiers](https://bit.ly/9-Proxy) |
| 10,000 GB | $0.68 | $6,800 \| [ see best per-GB enterprise rate](https://bit.ly/9-Proxy) |

**Bundles (IPs + traffic in one package)**

| Bundle | Contents | Price |
| --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 \| [ check the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 \| [ view the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 \| [ open the Pro bundle](https://bit.ly/9-Proxy) |

Enterprise also changes what you can do administratively, not just what you pay: unlimited data validity, a team mode with one owner plus up to five members, per-member traffic controls, full activity logs, and no-expiration bandwidth sharing inside the team. If you manage accounts on behalf of clients, that structure is the difference between one shared login and an actual permission model.

## The per-account math, done properly

Cost-per-IP and cost-per-GB only become meaningful when you divide them by accounts.

At the 100-IP tier, one IP per account works out to $0.24 per account. That includes unlimited traffic for that IP during its lifetime. At 500 IPs it drops to about $0.14 per account; at 5,000 it's roughly $0.07. If your accounts need genuinely separate identities rather than shared rotation, that second and third tier is where the value sits — the per-account price falls faster than the package price rises.

GB-based is arithmetic on consumption. If a single account session moves about 60 MB — a normal login, a few page loads, some API calls — then 100 GB covers somewhere around 1,600 sessions. If your sessions are heavy (dashboards, media, uploads), that number drops fast, and this is where people get surprised by their dashboard mid-month.

Two features reduce the burn on IP-based plans. First, unused IPs don't expire, so buying 5,000 doesn't force you to run 5,000 accounts this month. Second, the Today List lets you reuse any IP you've already forwarded within the last 24 hours without spending a new IP from your balance, provided that IP is still online. For anyone testing twenty account setups across a weekend, that materially stretches a package.

## Setting up a per-account workflow

The mechanics matter less than the mapping. What you want is a one-to-one relationship between a browser profile and an IP, held stable enough that the platform sees a consistent user.

1. **Decide the model before you buy.** Fixed sessions per account — IP-based. Rotation-heavy checks and scraping across many cities — GB-based. Both kinds of work in one team — a bundle.
2. **IP-based route:** install 9Proxy's desktop app, pick the IPs you want for the accounts you're running, and forward them. You get local addresses on distinct ports, which you paste into your anti-detect browser, emulator, or automation script. Nothing else needs proxy configuration at the application level.
3. **GB-based route:** generate endpoints in the dashboard, pick country, state, city, ZIP, or ISP, and choose sticky or rotating sessions. Export as `.txt` or `.csv`, or grab the ready-made code samples. Authentication is username/password or IP whitelisting.
4. **Map it down on paper.** Write down which profile uses which IP or session setting. When a platform asks for verification, you want to know instantly whether that account was on a stable sticky session or a rotating pool.
5. **Pair the proxy with an isolated browser.** A clean residential IP logged into an anti-detect profile is a consistent story. A clean residential IP logging into a browser that shares cookies and canvas fingerprints with three other accounts is still one device to the platform.
6. **Use sub-users and share codes if you're not solo.** Sub-users get their own credentials and assigned traffic; share codes let other people use your balance without your login. Enterprise adds the team structure with logging.

For mobile-first platforms, 9Proxy also ships ProxyHub — a device-management tool where ProxyHub Lite runs per device and ProxyHub Pro centralises control of multiple mobile proxies from a desktop. If you're handling app-based accounts rather than web logins, that's the piece worth testing early.

## Where this setup has limits

Nothing here is a guarantee against bans, and 9Proxy has documented limitations that matter more to account managers than to scrapers.

- **IP lifetime is residential-normal.** On IP-based plans, an IP runs a few hours up to roughly 24 hours. Accounts that expect a permanent static IP will see the address change. Plan the rotation around your login schedule rather than fighting it.
- **IP-based requires the desktop app.** GB-based works entirely from the dashboard, but per-IP unlimited bandwidth means installing software. If your workflow is cloud-only or headless, that's friction.
- **Coverage is 90+ countries, not 195.** Solid for US, UK, Europe, and Southeast Asia. Check your niche geography before committing a large balance.
- **No self-serve free trial on the site.** Trial access is offered on request through the provider's community channels, subject to availability, so budget a small paid test instead of expecting instant access.
- **Independent testing has limits.** Geekflare ran 300 requests against a Cloudflare-protected e-commerce target and reported 293 passes (97.7%), 5 CAPTCHAs, 2 hard blocks, and a 0.63-second average response time. A separate comparison site puts 9Proxy's tier-1 success rate at 95%+ but tier-2 at 85–92%, and flags thinner city-level pools — relevant if you rely on city-specific exits. It also notes budget-tier pools struggle on heavily protected targets like Amazon and high-volume Google SERP work.
- **Refund friction is the recurring complaint.** Geekflare attributes the provider's Trustpilot score to users who bought a plan that didn't suit their workload and couldn't recover the spend, rather than to network failures. Practically: test on the small tier first.

## Questions that come up before buying

**How many proxies do I need per account?** One IP per active session is the baseline for accounts that must not be linked. If several accounts share a device but never share a session window, some operators accept fewer IPs with disciplined rotation — but that's a risk decision, not a saving.

**IP-based or GB-based for social media and marketplace accounts?** IP-based for anything with a persistent logged-in session, because bandwidth is unlimited and the IP holds for hours. GB-based when you're doing short, spread-out checks across many locations.

**Will 9Proxy work with my anti-detect browser?** Yes — HTTP/HTTPS and SOCKS5 are supported, which covers anti-detect browsers, proxychains, and custom scripts. On GB plans you can also whitelist the device IP instead of using credentials.

**Do I need proxies *and* an anti-detect browser?** Yes, for anything where accounts share a device. The proxy separates network identity; the browser separates the fingerprint and cookie jar. Platforms analyse both.

**Can I split one balance across a team?** Yes. Sub-users with assigned traffic and share codes cover small teams; Enterprise adds one owner plus up to five members with per-member traffic limits and activity logs.

**What payment methods work?** Cards, crypto including USDT, BTC, ETH, LTC and DOGE, bank cards, Alipay, Apple Pay, and Google Pay, per the provider's own listing.

## The short version

For account management, the pricing model is the workflow decision. Unlimited bandwidth per IP suits accounts that stay logged in and move real traffic; per-GB suits short sessions spread thin across locations; bundles cover teams doing both. Get that mapping right and the rest — rotation timing, sticky sessions, fingerprint isolation — is configuration rather than crisis management.

If you want to see how the tiers line up against your actual account count, [👉 9Proxy's current plans and pricing are here](https://bit.ly/9-Proxy). Start on the small tier, run your real target environment against it for a few days, and let the block rate tell you whether you need the next one up.
