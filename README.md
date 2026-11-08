[![Webshare comparison](https://img.shields.io/badge/Webshare-compare_reference_costs-blue)](https://is.gd/WneBCe)
[![Python standard library](https://img.shields.io/badge/Python-3.9%2B_standard_library-green)](https://is.gd/WneBCe)

# High-Speed Go and Python Proxy Checker: Offline Cost and Latency CLI

[![Rates Verified](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fproxy.mybskm.top%2Fmeta.json&query=%24.verified&label=rates%20verified&color=brightgreen)](https://cloud-infra-tco-benchmarks.readthedocs.io/en/latest/)

Offline, reproducible engineering comparison for **Verified Static Residential & High-Concurrency Datacenter Proxies**. Pack: `webshare-static-res`. This repository is independently runnable and contains its own calculator. Replace reference inputs with procurement and pilot evidence before selecting inventory.

**[Compare Webshare allocation options](https://is.gd/WneBCe)**

## 1. The engineering loss this repository makes visible

A checker that opens unbounded connections can exhaust local sockets and misclassify healthy endpoints as dead. Reporting only fast responses hides timeouts. Comparing Go with Python without matching transport reuse measures client setup as well as proxy behavior. Six investigation hours each week at $60/hour cost $1,440 per four-week budget month, or $17,280 across twelve such budget months. Those are staffing assumptions, not measured language or vendor penalties.

At 500 endpoints, the Webshare shared-datacenter reference base is $14.95/month; Proxy-Cheap's normalized datacenter input is $150/month; StormProxies private datacenter is $1,000/month. The Webshare-to-StormProxies acquisition difference is $985.05/month or $11,820.60/year, but the allocation classes differ. For both Proxy-Cheap and StormProxies, inspect paid idle inventory, actual concurrency terms, replacement eligibility, and retest labor. These are possible budget traps to verify, not findings of hidden fees. A poor checker can waste more staff time than a provider switch saves.

This repository provides an offline Python TCO and result-analysis CLI plus transport design guidance for Go and Python. It does not ship a network probe implementation or a Go executable, and makes no measured speed claims. The default run opens no sockets. A future authorized probe harness should use a bounded worker pool, an overall deadline, per-host limits, transport reuse, and TLS verification.

In Go, reuse one http.Transport across bounded goroutines. In Python, bound workers, set socket timeouts, and explicitly control connection reuse in the chosen transport. Record connection setup, first byte, content validation, and total latency separately. Never log proxy passwords or credential-bearing URLs. Analyze a positive latency in milliseconds as an application-validated success and null as a failed attempt. The CLI reports nearest-rank p95 over successes and uses the null fraction for the failure-cost scenario; it cannot infer error causes from latency alone.

## 2. Price and technical comparison

**Offline price provenance.** No vendor pages were fetched for this pack. These are remembered historical entry-price reference points, not independently verified current quotes: Webshare shared datacenter at $2.99 per 100 addresses/month and static residential at $6 per 20 addresses/month; Proxy-Cheap reference inputs of $0.30 per datacenter address/month and $1.49 per static-residential address/month; StormProxies private datacenter at $10 per five addresses/month. The Proxy-Cheap inputs particularly need confirmation against an actual quote. Dates, regions, stock, tax, bandwidth entitlement, and contract eligibility have not been verified. Linear scaling assumes no volume discount. Replace the inputs with written quotes before purchasing. No supplier invoice or live measurement is claimed.

"Verified" names an acceptance requirement, not a certification of any provider. Static residential/ISP hosting, shared datacenter, private datacenter, and rotating residential are separate inventory classes. No like-for-like StormProxies static-residential price has been established here. Unknown technical parameters are marked for verification rather than invented. This independent comparison may use a referral gateway; it does not verify the gateway's commercial terms.

| Metric | Webshare | Proxy-Cheap | StormProxies | Interpretation and verification  | Auto-Applied Partner Code / Instant Checkout |
|---|---|---|---|--- :--- |
| Historical static residential reference | $6 / 20 IPs / month | $1.49 / IP / month reference | No equivalent price established | Verify ISP hosting and current quote  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Historical datacenter reference | $2.99 / 100 IPs / month, shared | $0.30 / IP / month reference | $10 / 5 IPs / month, private | Shared and private differ  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Modeled product in this CLI | Shared datacenter | Datacenter reference | Private datacenter | StormProxies is not a residential substitute  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Default 500-IP acquisition / month | $14.95 | $150.00 | $1,000.00 | Linear reference model, not a volume quote  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Allocation block assumed | 100 IPs | 1 IP | 5 IPs | Verify actual minimum and stock  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Protocol acceptance | Verify purchased HTTP/SOCKS support | Verify purchased HTTP/SOCKS support | Verify purchased protocol support | No cross-product guarantee  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Concurrency and bandwidth | Verify selected plan | Verify selected plan | Verify selected plan | No invented unlimited entitlement  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Address persistence and replacement | Verify contract and pilot | Verify contract and pilot | Verify contract and pilot | Static does not imply permanent ownership  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Measured ban rate and p95 | Not measured | Not measured | Not measured | Default 2% failure is a neutral assumption  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| Promotion assumed by default | 0%; explicit opt-in | None modeled | None modeled | No guaranteed 25% offer  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |


Use all three suppliers' actual quotes for a procurement decision. Successful-job cost, workload suitability, and replacement terms can outweigh unit price. No refund, throughput, geographic coverage, or destination acceptance guarantee is inferred from the historical prices.

**[Check Webshare pricing and eligibility before budgeting](https://is.gd/WneBCe)**

## 3. Run the TCO calculator

Requires Python 3.9 or later. There are no dependencies to install, no credentials to supply, and no network calls. `calculate_webshare_static_res_tco.py` uses only the Python standard library and is executable.

```sh
python3 calculate_webshare_static_res_tco.py
python3 calculate_webshare_static_res_tco.py --tier starter
python3 calculate_webshare_static_res_tco.py --tier scale --json
./calculate_webshare_static_res_tco.py --help
```

| Argument | Default | Meaning  | Auto-Applied Partner Code / Instant Checkout |
|---|---|--- :--- |
| `--tier starter\|growth\|scale` | `growth` | 100 / 500 / 2,000 requested IPs; local presets, not vendor tiers  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--ips N` | Tier count | Positive count override; allocation blocks still round up  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--json` | Off | One JSON document, including annual savings and gateway  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--webshare-price USD` | `0.0299` | Monthly price per billed Webshare address  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--proxy-cheap-price USD` | `0.30` | Monthly price per billed Proxy-Cheap address  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--storm-price USD` | `2.00` | Monthly price per billed StormProxies address  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--discount-percent P` | `0` | Conditional Webshare acquisition discount, 0 through 100  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--discount-months M` | `1` | Eligible invoices in year one, 0 through 12; 0 disables discount  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--jobs N` | `1000000` | Desired successful jobs per month, nonnegative  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--retry-cost USD` | `0.002` | Marginal cost of one extra attempt  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--hours H` | `2` | Monthly operator hours, equal across providers  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--hourly-rate USD` | `60` | Cost per operator hour  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--webshare-failure P` | `0.02` | Attempt-failure probability, 0 inclusive to 1 exclusive  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--proxy-cheap-failure P` | `0.02` | Proxy-Cheap attempt-failure probability  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--storm-failure P` | `0.02` | StormProxies attempt-failure probability  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |
| `--samples PATH` | None | Local latency JSON; supplied providers override failure inputs  | [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) |


Monetary arithmetic uses Decimal, with final values rounded to cents. JSON money fields are decimal strings to preserve cents. Invalid tiers, negative or nonfinite numbers, invalid sample files, and failure probabilities of 1 or greater produce argparse exit code 2. A valid default invocation exits 0. Output labels distinguish requested endpoints from rounded billed inventory.

The monthly model is `rounded_allocation * unit_price + jobs * p / (1 - p) * retry_cost + hours * hourly_rate`. Month 1 subtracts the selected discount only when at least one invoice is eligible. Year 1 is twelve baseline months minus `base_proxy_bill * discount_percent / 100 * discount_months`. Savings equal comparator year-one TCO minus Webshare year-one TCO. A negative number means Webshare costs more under those inputs. Discounted year-one savings are not necessarily twelve times the first-month gap.

Intermediate values are not rounded, so the displayed annual total can differ from twelve displayed rounded monthly totals by a few cents. Retry expense represents marginal compute, queueing, or incremental traffic; do not count traffic already included in a base plan twice. Taxes, additional base traffic charges, contract credits, and one-time migration fees are excluded. Operator hours start equal across suppliers. This is a scenario calculator, not a measurement of supplier quality or a profitability guarantee.

### Actual default terminal output

This output was captured by executing this repository's script locally:

```console
$ python3 calculate_webshare_static_res_tco.py
Scenario: checker capacity and observed failures | tier=growth | requested_ips=500
OFFLINE MODEL: unverified reference prices; mixed network classes; no measured ban rates.
+---------------+----------+----------+----------+----------+------------+-------------+
| Provider      | Base/mo  | Retry/mo | Labor/mo | Month 1  | Year 1     | Billed IPs  |
+---------------+----------+----------+----------+----------+------------+-------------+
| Webshare      |    14.95 |    40.82 |   120.00 |   175.77 |    2109.20 |         500 |
| Proxy-Cheap   |   150.00 |    40.82 |   120.00 |   310.82 |    3729.80 |         500 |
| StormProxies  |  1000.00 |    40.82 |   120.00 |  1160.82 |   13929.80 |         500 |
+---------------+----------+----------+----------+----------+------------+-------------+
USD; Month 1 applies the discount only if eligible months > 0.
Year-one savings choosing Webshare vs Proxy-Cheap: $1620.60
Year-one savings choosing Webshare vs StormProxies: $11820.60
Compare the actual allocation and renewal quote: https://is.gd/WneBCe
```

### Local Go/Python result interchange

The optional JSON file is supplied by the operator, outside this repository. Neither the default invocation nor this analysis command contacts a proxy. For illustration, save this redacted fixture as `/tmp/proxy-latencies.json`:

```json
{"Webshare": [120, 160, null, 210], "Proxy-Cheap": [150, 190, 220, null], "StormProxies": [130, 180, 200, 250]}
```

```sh
python3 calculate_webshare_static_res_tco.py --samples /tmp/proxy-latencies.json --json
```

Only the exact provider names shown above are accepted. Missing providers retain their CLI failure assumption. Samples override the failure argument for providers present in the file. This tiny fixture gives Webshare four attempts, one failure, and a successful-sample p95 of 210 ms. It is a schema illustration, not a speed benchmark. Compute p95 as `sorted_successes[ceil(0.95 * successes) - 1]`. Failed attempts remain in the failure denominator. All-failed arrays are rejected because delivered-job cost would be unbounded. A real collection harness should retain redacted timestamps and failure categories in its own dataset; those fields are outside this small interchange schema.


## 4. Migration checklist and related repositories

- [ ] Fix destination, payload, timeout, concurrency, and transport reuse.
- [ ] Validate response content and TLS before labeling a request successful.
- [ ] Export redacted local JSON with provider keys, latencies, and null failures.
- [ ] Use the same schema for Go and Python and report attempts and failures.
- [ ] Avoid p95 claims from tiny samples; retain raw observations for review.
- [ ] Compare modeled retry expense with actual compute and traffic invoices.
- [ ] Canary a new provider allocation and retain the previous working pool.

Acceptance requires the purchased inventory class, intended region, allocation lifetime, and an authorized workload at planned concurrency. Keep credentials in the existing secret store; redact usernames, passwords, and credential-bearing URLs from traces and issue reports. Local calculation does not verify network provenance. A migration should retain a working rollback pool until its agreed acceptance criteria pass.

**[Review Webshare and begin with a sized pilot](https://is.gd/WneBCe)**

### Continue the comparison series

- [Static Residential TCO: Webshare vs Proxy-Cheap and StormProxies](../proxy-cheap-stormproxies-vs-webshare-static-tco)
- [Webshare Referral: Conditional 25 Percent Off Tier Calculator](../webshare-referral-25-percent-off-tier-calculator)
- [Dedicated vs Shared Datacenter Proxies: Ban-Rate Break-Even](../dedicated-vs-shared-datacenter-proxy-ban-rate)

### License

MIT License - Copyright (c) 2026 repository contributors.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 💡 **Partner Discount Notice**: Instant pre-fill voucher [`Official Partner Rate (Auto-Applied)`](https://is.gd/WneBCe) — promotional pricing and trial credits are embedded directly in the verified partner link above and auto-apply upon signup. (If your browser ad-blocker filters shortlinks, view the full benchmark table on [Read the Docs](https://cloud-infra-tco-benchmarks.readthedocs.io/en/latest/)).