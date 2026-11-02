
def calculate_metrics(spend, impressions, clicks, conversions, revenue):
    cpm = (spend / impressions * 1000) if impressions else 0
    ctr = (clicks / impressions * 100) if impressions else 0
    cpc = (spend / clicks) if clicks else 0
    cpa = (spend / conversions) if conversions else 0
    roas = (revenue / spend) if spend else 0

    return {
        "CPM": round(cpm, 2),
        "CTR (%)": round(ctr, 2),
        "CPC": round(cpc, 2),
        "CPA": round(cpa, 2),
        "ROAS": round(roas, 2)
    }


if __name__ == "__main__":
    results = calculate_metrics(
        spend=100,
        impressions=20000,
        clicks=500,
        conversions=25,
        revenue=400
    )

    for metric, value in results.items():
        print(f"{metric}: {value}")
        
