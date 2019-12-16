## Introduction <a name="preface"></a>

### What are the insights of this data story?

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%;" w3-include-html="plots/wordcloud2.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Since the Neolithic Revolution, agriculture **feeds the world's population**. Even today, the agricultural sector **employs a large part of humanity** and is a **major point of the economy** of developed and developing countries. In the history of mankind, the **economic growth of countries** has almost always been accompanied by the development of agriculture and the **agricultural economy**, *i.e.* **production, imports and exports**.

<div style="clear: right; width: 100%;"></div>

### Which important events had a significant influence on the agriculture and the economy for the historical period from 1970 to 2015?

<div style="float: left; width: 45%; margin: 5% 5% 5% 5%;" w3-include-html="plots/ussrdiss.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; There was the **Cold war** from 1945 to 1990 with two **economic superpowers** (USA and USSR). The USSR had been dissolved in 1991. The Japanese economic miracle occured from 1945 to 1990 and allowed Japan to come out of the disastrous state in which it was at the exit of the WW2 and become one of the worlds largest economies. There have been 2 big oil crises, in 1973 and 1979. There have been many wars (Middle East wars 1973-2000 e.g. Yom Kippur War 1973, Islamic Revolution in Iran 1979, Iran–Iraq war 1980-1988, Gulf war 1990-1991, Yugoslav wars 1991-2001...). The **third Agricultural Revolution** (also known as Green revolution) occurs form 1960 to 1990 and improved agricultural productions thanks to fertilizers and chemicals.

<div style="clear: left; width: 100%;"></div>

### Which countries have highest GDP? How did GDP evolved during the last decades?

<div style="float: right; width: 100%; margin: 5% 0% 5% 0%;"> 
  <div class="slidecontainer">
    <input type="range" min="1970" max="2015" value="2000" class="slider" id="myRange">
    <span id="map"></span>
  </div>
  <script>
    var slider = document.getElementById("myRange");
    var output = document.getElementById("map");
    output.innerHTML = 'GDP in the world in '+slider.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/'+slider.value.toString()+'GDP.html" ></object>';
    slider.oninput = function() {
      output.innerHTML = 'GDP in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/'+this.value.toString()+'GDP.html" ></object>'
    }
  </script>
  <style>
.slidecontainer {
  width: 100%;
}

.slider {
  -webkit-appearance: none;
  width: 100%;
  height: 15px;
  border-radius: 5px;
  background: #d3d3d3;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.slider:hover {
  opacity: 1;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In 1970, the countries with highest GDP were **United States**, **Germany**, **Japan**, **France**, **United Kingdom** and **Italy**. Japan overtook Germany in 1971. Around the 90s, Italy and UK have been fighting for 5th place in the ranking. From 1996 to 2006 the UK surpassed France. China entered the top 6 in 1999 in place of Italy and got 2nd in ranking in 2009. In average, **GDP increased** during this period.

<div style="clear: right; width: 100%;"></div>

### What is the structure of international trade ?

<div style="float: left; width: 100%; margin: 5% 0% 5% 0%;" w3-include-html="plots/clusters.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GDP is **highly correlated** from one country to another. Globally, they **almost all increased the same way**. This can be explained by the fact that the **global economy is highly interlinked** and countries have **strong enough trading relations** to make the GDP evolve the same way. Furthermore, one can identify **main regions** in which the trading relations are more important. Possibly the most obvious observation from this network graph is the clear distinction between **former Eastern Bloc** countries and the rest of the world. About half of the years of our dataset are during the **East-West divide** where there were **two clear global trade blocks**.

<div style="clear: left; width: 100%;"></div>

## Agricultural and economical features <a name="sources"></a>

### Which features are the most influential features on the Gross Domestic Product ? 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; We use **knowledge** based method and more **technical**,  data analysis algorithm, to select the feature. However we expect to see the most traded goods as the most influential ones.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; We find that the goods that most influences the GDP are **soybean, tomatoes, maize, wheat, cattle live animals and pigs** amongst other. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It is an interesting result that is easily understandable. Take **soybean** for example. This crop is one of the **most produced**. The mains exporter are the US, Brasil and Argentina and the main importer is China. Around **330 millions tonnes** of soybean was produced in 2018. It is vastly used to **feed animals**. It is thus coherent to see such an important good be selected by our model. We see also that wheat, oats, cattle live and pigs are present. This again is easily understandable. It is sufficient to look at our **eating habit** to convince ourself that those goods plays an important role in the GDP. Below is the full list of the selected features:

- Soybeans Crops Production tonnes
- Tomatoes Crops Production tonnes
- Maize Crops Production tonnes
- Turkeys Livestock production Head
- Maize Food export quantities tonnes
- Maize, green Food export quantities tonnes
- Wheat Food export quantities tonnes
- Cattle Live animals import quantities Head
- Oats Food import quantities tonnes
- Pigs Live animals import quantities Head
- Tomatoes Food import quantities tonnes
- Turkeys Live animals import quantities Head

## Global production <a name="results"></a>

### Which countries produce the features of interest?

MAPS PRODUCTION

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Globally, all features that we identified seem to **follow a common trend**. The **biggest producers** are in almost all categories **China, the USA and Brazil**. Russia, France, Spain, Germany seem to get closer to their volumes. The rest of Europe is situated in the second or third tier of producers as well as the other developed countries (Australia, Canada, south American countries). In the majority of categories, north and south African countries are situated in the same orders of magnitude as developed countries. A general trend to observe is that **central African countries seem to produce very few resources** in comparison to the rest of the world. The only feature going against this general description seems to be the **cattle**. The production of cattle appears to be **very well distributed** throughout the world. The production of pigs also seem well distributed throughout the world except for countries excluding pork from their diet for religious purposes. The phenomenon might be explained by the increased difficulty in transporting these goods. Live animals and meat **transport is much more complicated** than grain, vegetables or forage. Meaning that the countries would generally **produce what they need** in term of meat and rather import crops or vegetables.  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The general trend we observe is that **developed countries are bigger producers**. This makes sense considering how we selected these features. Our regression model gives us the features that are **connected with a high GDP** thus the features selected will be markers of rich countries.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; What can be found surprising is the **stability of the producer ranking** throughout the years. The top producers 50 years ago are still the top producers nowadays. It is also worth noting that globally, even though the ranking does not change, the **sheer production volume follows a growing trend**.

## Global Trade Balances <a name="balances"></a>

In this part, we want to pick out a few of the identified features and look at where in the world they are most exported from and imported to. 

### What is green maize?

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%;" w3-include-html="plots/greenmaize.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The feature that our model puts out as the highest weighed for predicting GDP is **green maize**. What is it? It’s maize that is mainly harvested so it can be either directly **fed to animals** or conserved through “silage” and fed to them in winter. Maize is native to **central America** and thanks to genetic selection and hybridization it can now be grown **everywhere in the world**. Among the forage foods that are grown for animal feed, they’re very **high energy and easy maintenance**, since they only need to be harvested once. They also require high fertilizer, herbicide and pesticide levels. Especially with the commercial adoption of genetically modified maize that is herbicide and pest resistant during the 90s, it has emerged as a very important animal feed.

<div style="clear: right; width: 100%;"></div>

### Which countries are net exporters of green maize?

MAPS GREEN MAIZE

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  We see that in 1980 no country in the world was a strong net exporter of green maize. Starting from the mid 80s the **United States** emerge as the main net exporter. During the 90s and into recent years, some more countries emerge that are net exporters, mainly in Europe. Globally, the United States stays the most important exporter of this agricultural product throughout the years, which is probably why our model identified it as a **strong predictor of GDP**.

### Which countries are net importers of tomatoes?

MAPS TOMATOES

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Being a tomato importer also seems to be a **good predictor of wealth for the state**. Tomatoes are one of the most **important vegetable crops produced worldwide**, only potatoes have a higher production. Looking through the timeline, we clearly see that almost all **highly industrialized nations are continuously importing tomatoes**. Especially the United States, France and Germany are importing large quantities each year. It's not a big surprise, since tomatoes are a **popular ingredient in many modern western recipes**, but **require a climate** that is not well suited for most of the United States or Northern Europe.

### evtl Graph production trend 1 developed country 1 other

### How is the self-suffiency score distributed for the selected features?

Unlike the production ranking, the self sufficiency score seems to be **pretty instable**. It is interesting to note that the countries which were by far **top producers do no stand out early on**. For instance China does not appear in the highest score until 1990. The most surprising results came from **African countries** such as South Africa, the United Republic of Tanzania, Nigeria and the Ivory Coast that constantly have a **score competing with the richest countries** which was unexpected. (***See import/export and production***). Even though the general trend tends to show that **richer countries are more independent**, there are **outliers** and the score seems to have a pretty **high variance**.

### -> Comparison with GDP??

### Link with exporters??

## Conclusion <a name="conclusion"></a>
