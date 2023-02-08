# Moties Toegelicht 

Op deze github page publiceer ik [samenvattingen](moties.md) van tweede kamer moties die ik heb laten samenvatten door GPT3.5. 

De samenvattingen komen tot stand door de motie in te lezen van de [API van de tweede kamer](https://opendata.tweedekamer.nl), waarna ik de text van de motie combineer met een prompt en deze door de GPT3.5 API af laat maken. 



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