# Hoe worden de samenvattingen gecreërd?


De samenvattingen komen tot stand door dagelijks voor alle moties:
- De moties in te lezen via de [API van de tweede kamer](https://opendata.tweedekamer.nl)
- een input prompt voor [GPT3.5](https://openai.com/blog/openai-api/) te creëren door de text van de motie te combineren met een zin die uitlegd wat gpt3 met de text moet doen (zie onderstaande code) 
- De input naar de [GPT3.5 API](https://openai.com/blog/openai-api/) te sturen om een samenvatting te creeren




De python code voor de API call:
```python
import openai
prompt = "\nSamenvatting van bovenstaande text en impact van de motie, kort en bondig:\n"
input = text_motie + prompt
completion = openai.Completion.create(engine=engine,
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