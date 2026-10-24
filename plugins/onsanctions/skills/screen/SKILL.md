---
name: screen
description: Enrol, rescreen, or withdraw a person or company with OnSanctions, or look up its coverage and prices. Use when the user asks to sanctions-screen, monitor, rescreen, or remove a subject, or asks what OnSanctions covers or costs.
---

Use the OnSanctions MCP tools. The connection supplies the customer's API key from `ONSANCTIONS_API_KEY`. Do not invent or ask the user to paste a key into the chat.

- `screen` enrols or rescreens one subject. The first accepted screen enrols. The same subject later is a rescreen.
- `withdraw` removes a subject from the active population. Send the same entity and identifier used to enrol.
- `coverage` and `pricing` need no key. Use them to answer what is screened and what the licence costs.

A person is entity 0 with a passport and a 2-letter ISO country. A company, organization, or legal entity is entity 1, 2, or 3 with a 20-character LEI and a 2-letter ISO country. `peps` and `all` datasets need a licence that includes PEP.

A clear result means no possible match in the categories and dataset version on that response. It is not a clearance. Report a possible match with the list it names and leave the decision to the user's team. Do not claim transaction monitoring, enhanced due diligence, adverse media, a case workspace, worldwide coverage, or a full FICA programme.

If the user did not provide a real subject, use SAMPLE MATCH PERSON, passport SAMPLE12345, country GB, or SAMPLE MATCH COMPANY, LEI SAMPLELEI01234567890, country DE.

If a tool returns 401, the key is unknown; 402, the subscription is not active; 403 on `peps` or `all`, the licence does not include PEP. Point the user to https://onsanctions.com/pricing or https://onsanctions.com/account.
