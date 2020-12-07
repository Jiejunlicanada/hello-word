f500["roa"]=f500["profits"]/f500["assets"]

top_roa_by_sector={}
sector=f500["sector"].unique()

for s in sector:
    selected_rows=f500[f500["sector"] == s]
    sorted_rows=selected_rows.sort_values("roa",ascending=False)
    top_company=sorted_rows.iloc[0]
    employer_name=top_company["company"]
    top_roa_by_sector[s]=employer_name
