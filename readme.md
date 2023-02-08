# Moties Toegelicht 

Op deze github page publiceer ik [samenvattingen](moties.md) van tweede kamer moties die ik heb laten samenvatten door GPT3.5. 

De samenvattingen worden gegenereerd door de tekst van een motie te combineren met een prompt en vervolgens door te sturen naar de [GPT API](https://openai.com/api/). De moties worden verkregen uit de [API van de tweede kamer](https://opendata.tweedekamer.nl).



De python code voor de API call:
```python
import openai
prompt = "\nSamenvatting van bovenstaande text en impact van de motie, kort en bondig:\n"
input = text_motie + prompt
completion = openai.Completion.create(engine="text-davinci-003",
                                      prompt=input,
                                      temperature=0.3, 
                                      max_tokens=180, 
                                      frequency_penalty=0.0,
                                      presence_penalty=0.0) 
summary = completion.choices[0].text
```


Limitaties huidige versie:
- Op dit moment kan deze tool nog geen samenvattingen maken van moties die zijn ingediend als .doc file
- De samenvattingen zijn niet gecontroleerd op juistheid

## Moties met GPT3.5 samenvattingen 

| Motie | Samenvatting | Link | Datum |
|-------|--------------|-------|--------|
| Motie van het lid Kops | De motie van het lid Kops verzoekt de regering de Klimaatwet in te trekken, met als doel de implementatie van de Europese klimaatwet. Als gevolg hiervan zal de Klimaatwet worden ingetrokken, wat een grote impact zal hebben op de Nederlandse wetgeving. | niet beschikbaar | 2023-02-08 |
| Motie van het lid Stoffer | Deze motie van het lid Stoffer verzoekt de regering om eerst vast te stellen wat de doelstelling voor 2030 betekent voor het beleid en of het bijbehorende maatregelenpakket sociaal-maatschappelijk aanvaardbaar en systeemtechnisch haalbaar is met behoud van een betrouwbare energievoorziening, voordat er een wetsvoorstel wordt ingediend om het streefdoel voor CO2-reductie in 2030 bindend te maken. Deze motie heeft als doel om ervoor te zorgen dat de doelstellingen voor de energietransit | niet beschikbaar | 2023-02-08 |
| Motie van het lid Teunissen c.s. | Deze motie vraagt de regering om de 'indirecte kostencompensatie ETS' definitief af te schaffen, met als doel de prijsprikkel van CO2-beprijzing te versterken. Dit zou de zeer vervuilende chemische, metaal- en papier- en kartonindustrieën helpen hun uitstoot te verminderen en de klimaatverandering tegen te gaan. | niet beschikbaar | 2023-02-08 |
| Motie van de leden Boucke en Grinwis | Deze motie verzoekt de regering om maatregelen te nemen om de negatieve klimaatimpact van voorstellen met financiële implicaties te beperken. Deze motie is bedoeld om ervoor te zorgen dat er voor voorstellen met een negatief CO2-saldo wordt gezorgd dat deze impact wordt beperkt. | niet beschikbaar | 2023-02-08 |
| Motie van het lid Maeijer over voldoende financiële middelen voor de transitie van gesloten naar open plaatsen  | niet beschikbaar | niet beschikbaar | 2023-02-07 |
| Motie van het lid Stoffer c.s. | Deze motie van het lid Stoffer c.s. vraagt de regering om te onderzoeken hoe een indringender toets op de representativiteit van belangenorganisaties binnen het huidige artikel 3:305a BW gerealiseerd kan worden. Deze motie heeft als doel om ervoor te zorgen dat belangenorganisaties die rechtszaken tegen de Staat aanspannen, representatief zijn en dat de direct belanghebbenden deze rechtszaken financieren. | niet beschikbaar | 2023-02-08 |
| Motie van de leden Dassen en Koekkoek | Deze motie verzoekt de regering om in het Belastingplan 2024 een grondslag te creëren voor het opleggen van heffingen aan bedrijven die onevenredig veel profiteren van een crisis. Deze motie zal helpen om de winsten van fossiele bedrijven te beperken en zal bijdragen aan de vermindering van de klimaatverandering. | niet beschikbaar | 2023-02-08 |
| Motie van het lid Kröger | Deze motie van het lid Kroger verzoekt de regering alle onderzoeken, analyses, onderliggende modellen en andere zaken die onderliggend zijn aan beleidsvoorstellen te laten uitgaan van de doelen die in het coalitieakkoord zijn opgenomen. Deze motie heeft als doel om ervoor te zorgen dat beleidsvoorstellen gericht zijn op het behalen van de doelen die in het coalitieakkoord zijn opgenomen. | niet beschikbaar | 2023-02-08 |
| Motie van het lid Verkuijlen c.s. over nadere regels over de veiligheid van hulpverleners en jeugdigen in gesloten accommodaties  | niet beschikbaar | niet beschikbaar | 2023-02-07 |
| Motie van het lid Teunissen c.s. | Deze motie vraagt de regering om een viataks in te voeren in het IBO Klimaat, met energiebesparing en verduurzaming als voorwaarden. Deze motie heeft als doel om een sterkere besparings- en verduurzamingsprikkel te creëren voor grote vervuilers, die momenteel minder betalen voor hun energie dan huishoudens en kleine ondernemers. | niet beschikbaar | 2023-02-08 |
| Motie van de leden Kwint en Westerveld over het concretiseren van het nee-tenzijprincipe bij de toepassing van vrijheidsbeperkende maatregelen  | niet beschikbaar | niet beschikbaar | 2023-02-07 |
| Motie van de leden Kwint en Westerveld over alle vormen van leefgeld in de jeugdzorg jaarlijks indexeren  | niet beschikbaar | niet beschikbaar | 2023-02-07 |
| Motie van de leden Teunissen en Van Raan | Deze motie verzoekt de regering om te onderzoeken wat een nationaal emissiebudget is dat in lijn is met de Europese NDC voor de 1,5 graaddoelstelling die is vastgelegd in het Parijsakkoord. Deze motie zal de regering aanzetten tot het nemen van actie om de klimaatverandering tegen te gaan. | niet beschikbaar | 2023-02-08 |
| Motie van de leden Thijssen en Kröger | Deze motie verzoekt de regering om een inventaris te maken van klimaatmaatregelen waarvan huishoudens met een laag of normaal inkomen het meest profiteren en van maatregelen waarbij de zwaarste lasten worden gedragen door de sterkste schouders en de grootste vervuilers. Deze inventaris moet worden opgenomen in 4 IBO's. Deze motie heeft als doel om een breed draagvlak te creëren voor de klimaattransitie door de baten ervan met name te laten landen bij huishoudens met een laag of normaal inkomen. | niet beschikbaar | 2023-02-08 |
| Motie van de leden Kröger en Thijssen | Deze motie roept de regering op om fossiele bedrijven uit te sluiten van subsidies wanneer zij hun winsten gebruiken voor de aankoop van eigen aandelen. Deze motie is gericht op het versterken van duurzame energie en het verminderen van de invloed van fossiele bedrijven op het milieu. | niet beschikbaar | 2023-02-08 |
