# Phase 4 Project: *The Met Museum Ivory Classification Project*

![Elephants walking in a savannah](https://github.com/rjpost20/Met-Ivory-Classification-Project/blob/main/data/AdobeStock_394201577.jpeg?raw=true)
Photo by <a href="https://stock.adobe.com/contributor/19000/mat-hayward?load_type=author&prev_url=detail" >Mat Hayward</a> on Adobe Stock

## By Ryan Posternak and Harrison Carter

Flatiron School, Full-Time Live NYC<br>
Project Presentation Date: August 5th, 2022<br>
Instructor: Joseph Mata

### Links

Presentation slidedeck PDF:

<br>

## Overview and Business Understanding

### Goal: Build a model for the WWF which can identify whether an image of a piece of artwork among the Met museum's collection consists of ivory or not

*This is a project for learning purposes. The World Wildlife Fund is not involved with this project in any way.*

Elephants are crucial not only as biological and cultural icons, but as keystone species in their ecosystems. Consisting of  three main species  - the African Forest elephant, the African Savanna elephant, and the Asian elephant - each serves myriad purposes in their respective environments such as habitat creation, seed dispersal, forest pathway creation, and brush cover management. In 1930, an estimated 10 million wild elephants existed on the African continent. But after decades of poaching, habitat loss, and other human interventions that number [declined to approximately 496,000](https://elephantswithoutborders.org/projects/great-elephant-census/) by 2007.

Each year, poachers kill an estimated 20,000 wild elephants according to the [WWF](https://www.worldwildlife.org/species/elephant). The vast majority of these killings are done for illegal trade, mainly consisting of the valuable tusks of the elephant - otherwise known as ivory. With so few elephants remaining, this poaching presents an existential threat to the continued survival of elephants on the planet. While great progress has been made recently, with many nations - including most consequently China in 2017 - banning the sale of ivory, there is still much work to be done. In countries such as Vietnam and Thailand, the sale of ivory is illegal in name only, with little or no enforcement and street vendors and jewelry shops alike brazenly filling their shelves with ivory products.

To combat the continued existence of the ivory trade, wildlife conservation organizations such as the WWF are tirelessly urging nations across the world to enact stricter legislation, but the emergence of online shopping and peer-to-peer marketplaces presents a challenging roadblock. Interpol's Environmental Crime Programme [issued a report](https://www.interpol.int/es/Noticias-y-acontecimientos/Noticias/2013/Online-ivory-trade-worth-millions-INTERPOL-report-reveals) that revealed that millions of dollars in potentially illegal ivory are listed on online auction sites every year. [A recent study](https://news.mongabay.com/2021/01/ivory-by-any-other-name-illegal-trade-thrives-on-ebay-study-finds/) by the Durrell Institute of Conservation and Ecology (DICE) in the U.K. found that the illegal ivory trade thrives on online peer-to-peer marketplaces as well.

Although on most major websites specific product listings can be searched for by keywords, there is no easy way to tell if ivory products are listed in postings under alternative names or pseudonyms. The aim of this project is to create a proof-of-concept for the WWF of a machine learning model that takes in image data of three-dimensional objects and artifacts and classifies them as being likely consisting of ivory or not. The WWF can then use this proof-of-concept as a starting point for a model that could prove beneficial in their collaboration with online marketplaces, auction sites, law enforcment agencies and wildlife NGOs to identify listings potentially containing illegal ivory products and flag them for further investigation.

<br>

## Understanding the Data

Data for this project was sourced from <a href="https://www.metmuseum.org/art/collection/search?pageSize=0&sortBy=Relevance&sortOrder=asc&searchField=All" >The Metropolitan Museum of Art in New York City</a>. The museum, which hosts a collection of nearly half a million paintings, drawings, sculptures, and other artifacts spanning over 5,000 years of history, has open-sourced data on nearly all of the items in their collection through their <a href="https://metmuseum.github.io" >Collection API</a>. The API is freely available for commercial and non-commercial use, and requires no API key to use the service.

For this project, we first searched for artifacts that have the word "ivory" listed among the object's medium(s). These artifacts formed the initial collection of ivory art pieces that we used to train our neural network. For non-ivory object images to train the neural network, we searched for objects that contained "ceramic" listed among the medium(s), as we reasoned that ceramic figures which be of a similar size and shape as most ivory objects, thus making them a difficult comparison against the ivory artifacts for the neural networks to classify.

<br>

![slide 4](https://github.com/rjpost20/Met-Ivory-Classification-Project/blob/main/slide_deck/slide_jpgs/Slide%204.jpeg?raw=true)

<br>

After further exploration of the data, we discovered that many of the artifacts in our initial collection of ivory objects (all artifacts listing ivory as a medium) contained many pieces where ivory was only a minor component of the design of the artifact. In many of these cases, even human analysis could not accurately determine whether ivory was a component of the artifact or not. For this reason, we decided to limit our collection of ivory artifacts that we passed into the models to objects where ivory was the sole/main component.

<br>

![Distribution_Number_Materials_Comprising_Artifacts_ReadMe.png](https://github.com/rjpost20/Met-Ivory-Classification-Project/blob/main/visualizations/Distribution_Number_Materials_Comprising_Artifacts_ReadMe.png?raw=true)

<br>

## Modeling and Results

Our highest scoring model, model 1, achieved a test accuracy score of 82.4%, an approximately 10% improvement over our baseline fully-connected neural network. Although model 1 achieved the highest test accuracy score, most of the other CNN models achieved very similar scores, so we cannot confidenly say that model 1 will consistenly outperform the others on new test data. The model performed best at classifying non-ivory objects, correctly classifying 299 out of 353 non-ivory objects (84.7%) on the test data. On ivory objects, it correctly classified 70 out of 353 artifacts (80.2%) on the test data.

<br>

![slide 6](https://github.com/rjpost20/Met-Ivory-Classification-Project/blob/main/slide_deck/slide_jpgs/Slide%206_readme.jpeg?raw=true)

<br>

## Conclusions, Recommendations, and Next Steps
