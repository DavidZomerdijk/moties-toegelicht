---
layout: default
---

Deze webpagina heeft als doel te laten zien hoe Large Language Models (zoals GPT3) ingezet kunnen worden om de Nederlandse politiek transparanter en inzichtelijker te maken. 


### Technische uitleg

De samenvattingen en implicaties komen tot stand door dagelijks voor alle moties:
- De moties in te lezen via de [API van de tweede kamer](https://opendata.tweedekamer.nl)
- Een input prompt voor [GPT3.5](https://openai.com/blog/openai-api/) te creëren door de text van de motie te combineren met een zin die uitlegd wat gpt3 met de text moet doen (zie onderstaande code) 
- De input naar de [GPT3.5 API](https://openai.com/blog/openai-api/) te sturen om een samenvatting van de motie en een samenvatting van de implicaties te creeren


De python code voor de API call:
~~~python
import openai

samenvatting_prompt = "Samenvatting van bovenstaande motie, kort en bondig:\n",
implicaties_prompt = "De gevolgen / implicaties van deze motie in 1 korte zin samengevat, beginnend met 'Als de motie wordt aangenomen dan' \n"

# text and onderwerp_motie are retrieved from the tweede kamer API
samenvatting_input = onderwerp_motie + '\n\n' + text_motie + '\n\n' + samenvatting_prompt
implicaties_input = onderwerp_motie + '\n\n' + text_motie + '\n\n' + implicaties_prompt

implicaties = openai.Completion.create(engine="text-davinci-003",
                                      prompt=input,
                                      temperature=0.3, 
                                      max_tokens=100, 
                                      frequency_penalty=0.0,
                                      presence_penalty=0.0).choices[0].text

samenvatting = openai.Completion.create(engine="text-davinci-003",
                                        prompt=input,
                                        temperature=0.3, 
                                        max_tokens=180, 
                                        frequency_penalty=0.0,
                                        presence_penalty=0.0).choices[0].text
~~~


### Limitaties huidige versie
- Op dit moment kan deze tool nog geen samenvattingen maken van moties die zijn ingediend als .doc file
- De samenvattingen zijn niet gecontroleerd op juistheid

### Backlog
- Extra attributen geven aan de motie
  - Namen indieners
  - Partijen indieners
  - Onderwerp (e.g duurzaamheid, huisvesting, etc.)
- Filter opties toevoegen
- Pagina maken met overzicht moties per tweede kamer lid
  - GPT3 Samenvatting laten maken van alle moties die dit kamerlid heeft ingediend
- .doc files kunnen inlezen