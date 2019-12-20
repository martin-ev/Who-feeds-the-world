## Introduction <a name="intro"></a>

### What are the insights of this data story?

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/wordcloud2.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Since the Neolithic Revolution, agriculture **feeds the world's population**. Even today, the agricultural sector **employs a large part of humanity** and is a **major part of the economy** of developed and developing countries. In the history of mankind, the **economic growth of countries** has almost always been accompanied by the development of agriculture and the **agricultural economy**, *i.e.* **production, imports and exports**. In this data story we want to explore different links between the agriculture and the economic success of countries. Which crops are produced and which animals are traded by richer countries? Do they tend to be net exporters or importers of food? Do they tend to be self-sufficient? We try to answer all of these questions and show many interesting insights along the way.

<div style="clear: right; width: 100%;"></div>

### Which important events had a significant influence on the agriculture and the economy for the historical period from 1970 to 2015?

<div style="float: left; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/ussrdiss.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; To be able to properly understand the studied data, we have to first look at the historical context of the period we are analyzing. There was the **Cold war** from 1945 to 1990 between the two **economic superpowers** (USA and USSR). The USSR was then dissolved in 1991. The Japanese economic miracle occured from 1945 to 1990 and allowed Japan to come out of the disastrous state in which it was at the exit of WW2 and become one of the worlds largest economies. There have been 2 big oil crises, in 1973 and 1979. There have also been many wars (Middle East wars 1973-2000 e.g. Yom Kippur War 1973, Islamic Revolution in Iran 1979, Iran–Iraq war 1980-1988, Gulf war 1990-1991, Yugoslav wars 1991-2001...). The **third Agricultural Revolution** (also known as Green revolution) occured form 1960 to 1990 and improved agricultural productions thanks to fertilizers and chemicals.

<div style="clear: left; width: 100%;"></div>

### Which countries have the highest GDP? How did GDP evolve during the last decades?

<div style="float: right; width: 100%; margin: 5% 0% 5% 0%;"> 
  <div class="slidecontainer">
    <input type="range" min="1970" max="2014" value="2000" class="slider" id="myRange">
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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In 1970, the countries with the highest GDP were **United States**, **Germany**, **Japan**, **France**, **United Kingdom** and **Italy**. Japan overtook Germany in 1971. Around the 90s, Italy and UK were fighting for 5th place in the ranking. From 1996 to 2006 the UK surpassed France. China entered the top 6 in 1999 in place of Italy and got 2nd in ranking in 2009. On average, **GDP continuously increased** during this period.

<div style="clear: right; width: 100%;"></div>

### What is the structure of international trade?

<div style="float: left; width: 100%; margin: 5% 0% 5% 0%;" w3-include-html="plots/clusters.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; This network shows just how **highly correlated** the evolution of GDP from one country to another is. Possibly the most obvious observation from this network graph is the clear distinction between **former Eastern Bloc** countries and the rest of the world. About half of the years of our dataset are during the **East-West divide** where there were **two clear global trade blocks**. Nevertheless, GPD **increased the same way** almost everywhere and the whole world is close to being a single big cluster. This can be explained by the fact that the **global economy is highly interlinked** and countries have **strong trading relations** which leads to the GDP evolving the same way. Global trade and thus interdependence has been continuously increasing throughout the past decades. There are many institutions put into place for this to be possible. Today, almost all countries worldwide are part of the **World Trade Organization**, which makes sure that tariffs and other barriers to trade are reduced. In the past years, we've also seen that many countries, especially the **United States**, are becoming increasingly more **sceptical of global trade** and even engage in **trade wars**. What kind of impacts could this have on the future of **international trade**? 

<div style="clear: left; width: 100%;"></div>

## About the dataset <a name="dataset"></a>

The data that we use for analysis comes from the **"Global Food & Agriculture Statistic"**. It is a dataset by the **Food and Agriculture Organization of the United Nations** and includes extensive information about many factors related to agriculture, such as production output, food prices, trade balances and environmental impacts among others. It includes countrywise yearly values from 1970 to 2015. 

## Our approach

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/inflationrates.html"></div>

How to measure economic success? The first and most intuitive is to use the **Gross Domestic Product** of countries. The second approach we took was **price stability**, expressed in low levels of inflation and thus small changes in the **Consumer Price Index**. Can we create a model that will tell us which products to produce and which to trade to **maximize for GDP** or **minimize for inflation**? As it turned out, price stability did not yield significant correlations to any production or trade. GDP however did... 

<div style="clear: right; width: 100%;"></div>

## Most important agricultural and economical features <a name="features"></a>

### Which features are the most influential features on the Gross Domestic Product? 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Using a **knowledge** based method as well as a more **technical**,  data analysis algorithm, we were able to select specific features. However, as we expect the most influential goods to not only have high correlation with GDP, but to also be globally relevant in production volume, we narrowed down our possible choice of features. With all of this, our model managed to pick out some features that could optimize GDP. 

Below is the full list of the selected features, sorted by order of importance attributed by the model:

- Maize, green Food export quantities tonnes
- Tomatoes Food import quantities tonnes
- Oats Food import quantities tonnes
- Pigs Live animals import quantities Head
- Turkeys Live animals import quantities Head
- Tomatoes Crops Production tonnes
- Cattle Live animals import quantities Head
- Maize Crops Production tonnes
- Soybeans Crops Production tonnes
- Wheat Food export quantities tonnes
- Turkeys Livestock production Head
- Maize Food export quantities tonnes





&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It is an interesting result that is easily understandable. Take **soybeans** for example. This crop is one of the **most produced** worldwide. The main exporters are the US, Brasil and Argentina and the main importer is China. Around **330 millions tonnes** of soybeans were produced in 2018. It is vastly used to **feed animals**. It is thus coherent to see such an important good selected by our model. We also see that wheat, oats, cattle live and pigs are present. This again is easily understandable. It is sufficient to look at our **eating habits** to convince ourselves that those goods plays an important role in GDP. Now that we've established which agricultural production and trade features are best at predicting a high GDP, we want to look further into which countries produce and trade them and try to derive further conclusions from that. 


## Global production <a name="production"></a>

### Which countries produce the features of interest?

<div style="float: right; width: 100%; margin: 5% 0% 5% 0%;">
  <style>
body {font-family: Arial;}

/* Style the tab */
.tabProd {
  overflow: hidden;
  border: 1px solid #ccc;
  background-color: #f1f1f1;
}

/* Style the buttons inside the tab */
.tabProd button {
  background-color: inherit;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 14px 16px;
  transition: 0.3s;
  font-size: 17px;
}

/* Change background color of buttons on hover */
.tabProd button:hover {
  background-color: #ddd;
}

/* Create an active/current tablink class */
.tabProd button.active {
  background-color: #ccc;
}

/* Style the tab content */
.tabcontentProd {
  display: none;
  padding: 6px 12px;
  border: 1px solid #ccc;
  border-top: none;
}

/* Style the close button */
.toprightProd {
  float: right;
  cursor: pointer;
  font-size: 28px;
}

.toprightProd:hover {color: red;}
</style>

<div class="tabProd">
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdCattle')" id="defaultOpenProd">Cattle</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdMaize')">Maize</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdGreenmaize')">Green maize</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdOats')">Oats</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdPigs')">Pigs</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdSoybeans')">Soybeans</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdTomatoes')">Tomatoes</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdTurkeys')">Turkeys</button>
  <button class="tablinksProd" onclick="openCityProd(event, 'ProdWheat')">Wheat</button>
</div>

<div id="ProdCattle" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdCattle">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdCattle" id="myRangeProdCattle">
    <span id="mapProdCattle"></span>
  </div>
  <script>
    var sliderProdCattle = document.getElementById("myRangeProdCattle");
    var outputProdCattle = document.getElementById("mapProdCattle");
    outputProdCattle.innerHTML = 'Production of cattle (livestock) in the world in '+sliderProdCattle.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Cattle Livestock production Head_'+sliderProdCattle.value.toString()+'.html" ></object>';
    sliderProdCattle.oninput = function() {
      outputProdCattle.innerHTML = 'Production of cattle (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Cattle Livestock production Head_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdCattle {
  width: 100%;
}

.sliderProdCattle {
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

.sliderProdCattle:hover {
  opacity: 1;
}

.sliderProdCattle::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdCattle::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdMaize" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdMaize">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdMaize" id="myRangeProdMaize">
    <span id="mapProdMaize"></span>
  </div>
  <script>
    var sliderProdMaize = document.getElementById("myRangeProdMaize");
    var outputProdMaize = document.getElementById("mapProdMaize");
    outputProdMaize.innerHTML = 'Production of maize (crops) in the world in '+sliderProdMaize.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize Crops Production tonnes_'+sliderProdMaize.value.toString()+'.html" ></object>';
    sliderProdMaize.oninput = function() {
      outputProdMaize.innerHTML = 'Production of maize (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdMaize {
  width: 100%;
}

.sliderProdMaize {
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

.sliderProdMaize:hover {
  opacity: 1;
}

.sliderProdMaize::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdMaize::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdGreenmaize" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdGreenmaize">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdGreenmaize" id="myRangeProdGreenmaize">
    <span id="mapProdGreenmaize"></span>
  </div>
  <script>
    var sliderProdGreenmaize = document.getElementById("myRangeProdGreenmaize");
    var outputProdGreenmaize = document.getElementById("mapProdGreenmaize");
    outputProdGreenmaize.innerHTML = 'Production of green maize (crops) in the world in '+sliderProdGreenmaize.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green Crops Production tonnes_'+sliderProdGreenmaize.value.toString()+'.html" ></object>';
    sliderProdGreenmaize.oninput = function() {
      outputProdGreenmaize.innerHTML = 'Production of green maize (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdGreenmaize {
  width: 100%;
}

.sliderProdGreenmaize {
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

.sliderProdGreenmaize:hover {
  opacity: 1;
}

.sliderProdGreenmaize::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdGreenmaize::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdOats" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdOats">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdOats" id="myRangeProdOats">
    <span id="mapProdOats"></span>
  </div>
  <script>
    var sliderProdOats = document.getElementById("myRangeProdOats");
    var outputProdOats = document.getElementById("mapProdOats");
    outputProdOats.innerHTML = 'Production of oats (crops) in the world in '+sliderProdOats.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Oats Crops Production tonnes_'+sliderProdOats.value.toString()+'.html" ></object>';
    sliderProdOats.oninput = function() {
      outputProdOats.innerHTML = 'Production of oats (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Oats Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdOats {
  width: 100%;
}

.sliderProdOats {
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

.sliderProdOats:hover {
  opacity: 1;
}

.sliderProdOats::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdOats::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdPigs" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdPigs">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdPigs" id="myRangeProdPigs">
    <span id="mapProdPigs"></span>
  </div>
  <script>
    var sliderProdPigs = document.getElementById("myRangeProdPigs");
    var outputProdPigs = document.getElementById("mapProdPigs");
    outputProdPigs.innerHTML = 'Production of pigs (livestock) in the world in '+sliderProdPigs.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Pigs Livestock production Head_'+sliderProdPigs.value.toString()+'.html" ></object>';
    sliderProdPigs.oninput = function() {
      outputProdPigs.innerHTML = 'Production of pigs (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Pigs Livestock production Head_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdPigs {
  width: 100%;
}

.sliderProdPigs {
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

.sliderProdPigs:hover {
  opacity: 1;
}

.sliderProdPigs::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdPigs::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdSoybeans" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdSoybeans">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdSoybeans" id="myRangeProdSoybeans">
    <span id="mapProdSoybeans"></span>
  </div>
  <script>
    var sliderProdSoybeans = document.getElementById("myRangeProdSoybeans");
    var outputProdSoybeans = document.getElementById("mapProdSoybeans");
    outputProdSoybeans.innerHTML = 'Production of soybeans (crops) in the world in '+sliderProdSoybeans.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Soybeans Crops Production tonnes_'+sliderProdSoybeans.value.toString()+'.html" ></object>';
    sliderProdSoybeans.oninput = function() {
      outputProdSoybeans.innerHTML = 'Production of soybeans (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Soybeans Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdSoybeans {
  width: 100%;
}

.sliderProdSoybeans {
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

.sliderProdSoybeans:hover {
  opacity: 1;
}

.sliderProdSoybeans::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdSoybeans::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdTomatoes" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdTomatoes">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdTomatoes" id="myRangeProdTomatoes">
    <span id="mapProdTomatoes"></span>
  </div>
  <script>
    var sliderProdTomatoes = document.getElementById("myRangeProdTomatoes");
    var outputProdTomatoes = document.getElementById("mapProdTomatoes");
    outputProdTomatoes.innerHTML = 'Production of tomatoes (crops) in the world in '+sliderProdTomatoes.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes Crops Production tonnes_'+sliderProdTomatoes.value.toString()+'.html" ></object>';
    sliderProdTomatoes.oninput = function() {
      outputProdTomatoes.innerHTML = 'Production of tomatoes (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdTomatoes {
  width: 100%;
}

.sliderProdTomatoes {
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

.sliderProdTomatoes:hover {
  opacity: 1;
}

.sliderProdTomatoes::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdTomatoes::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdTurkeys" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdTurkeys">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdTurkeys" id="myRangeProdTurkeys">
    <span id="mapProdTurkeys"></span>
  </div>
  <script>
    var sliderProdTurkeys = document.getElementById("myRangeProdTurkeys");
    var outputProdTurkeys = document.getElementById("mapProdTurkeys");
    outputProdTurkeys.innerHTML = 'Production of turkeys (livestock) in the world in '+sliderProdTurkeys.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Turkeys Livestock production Head_'+sliderProdTurkeys.value.toString()+'.html" ></object>';
    sliderProdTurkeys.oninput = function() {
      outputProdTurkeys.innerHTML = 'Production of turkeys (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Turkeys Livestock production Head_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdTurkeys {
  width: 100%;
}

.sliderProdTurkeys {
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

.sliderProdTurkeys:hover {
  opacity: 1;
}

.sliderProdTurkeys::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdTurkeys::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="ProdWheat" class="tabcontentProd">
  <span onclick="this.parentElement.style.display='none'" class="toprightProd">X</span>
  <div class="slidecontainerProdWheat">
    <input type="range" min="1970" max="2014" value="2000" class="sliderProdWheat" id="myRangeProdWheat">
    <span id="mapProdWheat"></span>
  </div>
  <script>
    var sliderProdWheat = document.getElementById("myRangeProdWheat");
    var outputProdWheat = document.getElementById("mapProdWheat");
    outputProdWheat.innerHTML = 'Production of wheat (crops) in the world in '+sliderProdWheat.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Wheat Crops Production tonnes_'+sliderProdWheat.value.toString()+'.html" ></object>';
    sliderProdWheat.oninput = function() {
      outputProdWheat.innerHTML = 'Production of wheat (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Wheat Crops Production tonnes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerProdWheat {
  width: 100%;
}

.sliderProdWheat {
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

.sliderProdWheat:hover {
  opacity: 1;
}

.sliderProdWheat::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderProdWheat::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>

<script>
function openCityProd(evt, cityNameProd) {
  var iProd, tabcontentProd, tablinksProd;
  tabcontentProd = document.getElementsByClassName("tabcontentProd");
  for (iProd = 0; iProd < tabcontentProd.length; iProd++) {
    tabcontentProd[iProd].style.display = "none";
  }
  tablinksProd = document.getElementsByClassName("tablinksProd");
  for (iProd = 0; iProd < tablinksProd.length; iProd++) {
    tablinksProd[iProd].className = tablinksProd[iProd].className.replace(" active", "");
  }
  document.getElementById(cityNameProd).style.display = "block";
  evt.currentTarget.className += " active";
}

// Get the element with id="defaultOpenProd" and click on it
document.getElementById("defaultOpenProd").click();
</script>  
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Globally, all features that we identified seem to **follow a common trend**. The **biggest producers** are in almost all categories **China, the USA and Brazil**. Russia, France, Spain, Germany seem to get closer to their volumes. The rest of Europe is situated in the second or third tier of producers as well as the other developed countries (Australia, Canada, south American countries). In the majority of categories, north and south African countries are situated in the same orders of magnitude as developed countries. A general trend to observe is that **central African countries seem to produce very few resources** in comparison to the rest of the world. The only feature going against this general description seems to be **cattle**. The production of cattle appears to be **very well distributed** throughout the world. The production of pigs also seems well distributed throughout the world except for countries excluding pork from their diet for religious purposes. The phenomenon might be explained by the increased difficulty in transporting these goods. Live animals and meat **transport is much more complicated** than grain, vegetables or forage. Meaning that the countries would generally **produce what they need** in terms of meat and rather import crops or vegetables.  

<div style="float: left; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/barplotcattleprod.html"></div>

<div style="clear: left; width: 100%;"></div>


### Are big producers wealthier? 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The general trend we observe is that **developed countries are bigger producers**. This makes sense considering how we selected these features. Our regression model gives us the features that are **connected with a high GDP** thus the features selected will be markers of rich countries. 


### Is the production of important items stable? 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; What can be found surprising is the **stability of the producer ranking** throughout the years. The top producers 50 years ago are still the top producers nowadays. It is also worth noting that globally, even though the ranking does not change much, the **sheer production volume follows a growing trend**.

## Global Trade Balances <a name="balances"></a>

In this part, we want to pick out a few of the identified features and look at where in the world they are most exported from and imported to. 

### What is green maize?

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/greenmaize.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The feature that our model puts out as the highest weighed for predicting GDP is **green maize**. What is it? It’s maize that is mainly harvested so it can be either directly **fed to animals** or conserved through “silage” and fed to them in winter. Maize is native to **central America** and thanks to genetic selection and hybridization it can now be grown **everywhere in the world**. Among the forage foods that are grown for animal feed, they’re very **high energy and easy maintenance**, since they only need to be harvested once. They also require high fertilizer, herbicide and pesticide levels. Especially with the commercial adoption of genetically modified maize that is herbicide and pest resistant during the 90s, it has emerged as a very important animal feed.

<div style="clear: right; width: 100%;"></div>

### Which countries are net exporters of green maize?

<div class="slidecontainerTradeGreenmaizeAlone">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeGreenmaizeAlone" id="myRangeTradeGreenmaizeAlone">
    <span id="mapTradeGreenmaizeAlone"></span>
  </div>
  <script>
    var sliderTradeGreenmaizeAlone = document.getElementById("myRangeTradeGreenmaizeAlone");
    var outputTradeGreenmaizeAlone = document.getElementById("mapTradeGreenmaizeAlone");
    outputTradeGreenmaizeAlone.innerHTML = 'Trade Balance of green maize (crops) in the world in '+sliderTradeGreenmaizeAlone.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green_'+sliderTradeGreenmaizeAlone.value.toString()+'.html" ></object>';
    sliderTradeGreenmaizeAlone.oninput = function() {
      outputTradeGreenmaizeAlone.innerHTML = 'Trade Balance of green maize (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeGreenmaizeAlone {
  width: 100%;
}

.sliderTradeGreenmaizeAlone {
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

.sliderTradeGreenmaizeAlone:hover {
  opacity: 1;
}

.sliderTradeGreenmaizeAlone::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeGreenmaizeAlone::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/maizenettrade.html"></div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  We see that until the 80s no country in the world was a strong net exporter of green maize. It was barely even exported or imported in any country. Starting from the mid 80s the **United States** emerge as the main net exporter. During the 90s and into recent years, some more countries emerge that are net exporters, mainly in Europe. Globally, the United States stays the single most important exporter of this agricultural product throughout the years, which is probably why our model identified it as the **strongest predictor of GDP**.

<div style="clear: right; width: 100%;"></div>

### Which countries are net importers of tomatoes?

<div class="slidecontainerTradeTomatoesAlone">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeTomatoesAlone" id="myRangeTradeTomatoesAlone">
    <span id="mapTradeTomatoesAlone"></span>
  </div>
  <script>
    var sliderTradeTomatoesAlone = document.getElementById("myRangeTradeTomatoesAlone");
    var outputTradeTomatoesAlone = document.getElementById("mapTradeTomatoesAlone");
    outputTradeTomatoesAlone.innerHTML = 'Trade Balance of tomatoes (crops) in the world in '+sliderTradeTomatoesAlone.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes_'+sliderTradeTomatoesAlone.value.toString()+'.html" ></object>';
    sliderTradeTomatoesAlone.oninput = function() {
      outputTradeTomatoesAlone.innerHTML = 'Trade Balance of tomatoes (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeTomatoesAlone {
  width: 100%;
}

.sliderTradeTomatoesAlone {
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

.sliderTradeTomatoesAlone:hover {
  opacity: 1;
}

.sliderTradeTomatoesAlone::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeTomatoesAlone::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Being a tomato importer, but also a tomato producer seems to be a **good predictor of wealth for the state**. Tomatoes are one of the most **important vegetable crops produced worldwide**, only potatoes have a higher production. Looking through the timeline, we clearly see that almost all **highly industrialized nations are continuously importing tomatoes**. Especially the United States, France and Germany are importing large quantities each year. It's not a big surprise, since tomatoes are a **popular ingredient in many modern western recipes**, but **require a climate** that is not well suited for most of the United States or Northern Europe.

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/tomatoesimports.html"></div>


### What can we say about the other trade features of interest?

Just as we've seen for the production, the trade balances of our features also follow some broader **trends**. To start off, without even looking at the maps yet, but at the identified trade features, we see that many of them are directly or indirectly related to **animal products**. Imports of live pigs, turkeys and cattle are some of the highest on the list. Other than that, as we've already established, green maize as well as soybeans are mainly grown for **animal feed**. In addition to those, even for **oats**, the primary use was for livestock feeding (**70% of global production** in 2009, according to the FAO). What about the others? Even though we might not think about these crops primarily as feeding stuff, regular **maize and wheat** are also significantly used for this purpose. They are indeed both major staple foods for people, but especially in developed countries, they are also a major feedstuff. According to the FAO, in 2007 around 16% of global **wheat production** was used to feed animals, whereas this number was **42% for the EU**.



### Live animals on ships?

<div style="float: left; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/shippingcontainer.html"></div>

Even though many **animal rights activists** are strongly campaigning against it, **millions of live animals** are being transported in gruesome conditions around the world every year. Their final destination is usually the slaughterhouse. When countries income level rises, the **demand for meat** increases with it. Meat consumption is regarded as a symbol of wealth across cultures. The economic benefits of transporting the animals alive is twofold: on one hand, the costs are reduced, since the it is more **expensive to keep the meat frozen** during transport and on the other hand, consumers usually prefer their meat as fresh as possible. The live trade industry is booming so it's no surprise that many of the strongest features identified by our model come from it. 

<div style="clear: left; width: 100%;"></div>

### Who imports and exports them?

<div style="float: right; width: 100%; margin: 5% 0% 5% 0%;">
  <style>
body {font-family: Arial;}

/* Style the tab */
.tabTrade {
  overflow: hidden;
  border: 1px solid #ccc;
  background-color: #f1f1f1;
}

/* Style the buttons inside the tab */
.tabTrade button {
  background-color: inherit;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 14px 16px;
  transition: 0.3s;
  font-size: 17px;
}

/* Change background color of buttons on hover */
.tabTrade button:hover {
  background-color: #ddd;
}

/* Create an active/current tablink class */
.tabTrade button.active {
  background-color: #ccc;
}

/* Style the tab content */
.tabcontentTrade {
  display: none;
  padding: 6px 12px;
  border: 1px solid #ccc;
  border-top: none;
}

/* Style the close button */
.toprightTrade {
  float: right;
  cursor: pointer;
  font-size: 28px;
}

.toprightTrade:hover {color: red;}
</style>

<div class="tabTrade">
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeCattle')" id="defaultOpenTrade">Cattle</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeMaize')">Maize</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeGreenmaize')">Green maize</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeOats')">Oats</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradePigs')">Pigs</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeSoybeans')">Soybeans</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeTomatoes')">Tomatoes</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeTurkeys')">Turkeys</button>
  <button class="tablinksTrade" onclick="openCityTrade(event, 'TradeWheat')">Wheat</button>
</div>

<div id="TradeCattle" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeCattle">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeCattle" id="myRangeTradeCattle">
    <span id="mapTradeCattle"></span>
  </div>
  <script>
    var sliderTradeCattle = document.getElementById("myRangeTradeCattle");
    var outputTradeCattle = document.getElementById("mapTradeCattle");
    outputTradeCattle.innerHTML = 'Trade Balance of cattle (livestock) in the world in '+sliderTradeCattle.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Cattle_'+sliderTradeCattle.value.toString()+'.html" ></object>';
    sliderTradeCattle.oninput = function() {
      outputTradeCattle.innerHTML = 'Trade Balance of cattle (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Cattle_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeCattle {
  width: 100%;
}

.sliderTradeCattle {
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

.sliderTradeCattle:hover {
  opacity: 1;
}

.sliderTradeCattle::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeCattle::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeMaize" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeMaize">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeMaize" id="myRangeTradeMaize">
    <span id="mapTradeMaize"></span>
  </div>
  <script>
    var sliderTradeMaize = document.getElementById("myRangeTradeMaize");
    var outputTradeMaize = document.getElementById("mapTradeMaize");
    outputTradeMaize.innerHTML = 'Trade Balance of maize (crops) in the world in '+sliderTradeMaize.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize_'+sliderTradeMaize.value.toString()+'.html" ></object>';
    sliderTradeMaize.oninput = function() {
      outputTradeMaize.innerHTML = 'Trade Balance of maize (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeMaize {
  width: 100%;
}

.sliderTradeMaize {
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

.sliderTradeMaize:hover {
  opacity: 1;
}

.sliderTradeMaize::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeMaize::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeGreenmaize" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeGreenmaize">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeGreenmaize" id="myRangeTradeGreenmaize">
    <span id="mapTradeGreenmaize"></span>
  </div>
  <script>
    var sliderTradeGreenmaize = document.getElementById("myRangeTradeGreenmaize");
    var outputTradeGreenmaize = document.getElementById("mapTradeGreenmaize");
    outputTradeGreenmaize.innerHTML = 'Trade Balance of green maize (crops) in the world in '+sliderTradeGreenmaize.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green_'+sliderTradeGreenmaize.value.toString()+'.html" ></object>';
    sliderTradeGreenmaize.oninput = function() {
      outputTradeGreenmaize.innerHTML = 'Trade Balance of green maize (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Maize, green_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeGreenmaize {
  width: 100%;
}

.sliderTradeGreenmaize {
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

.sliderTradeGreenmaize:hover {
  opacity: 1;
}

.sliderTradeGreenmaize::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeGreenmaize::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeOats" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeOats">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeOats" id="myRangeTradeOats">
    <span id="mapTradeOats"></span>
  </div>
  <script>
    var sliderTradeOats = document.getElementById("myRangeTradeOats");
    var outputTradeOats = document.getElementById("mapTradeOats");
    outputTradeOats.innerHTML = 'Trade Balance of oats (crops) in the world in '+sliderTradeOats.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Oats_'+sliderTradeOats.value.toString()+'.html" ></object>';
    sliderTradeOats.oninput = function() {
      outputTradeOats.innerHTML = 'Trade Balance of oats (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Oats_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeOats {
  width: 100%;
}

.sliderTradeOats {
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

.sliderTradeOats:hover {
  opacity: 1;
}

.sliderTradeOats::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeOats::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradePigs" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradePigs">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradePigs" id="myRangeTradePigs">
    <span id="mapTradePigs"></span>
  </div>
  <script>
    var sliderTradePigs = document.getElementById("myRangeTradePigs");
    var outputTradePigs = document.getElementById("mapTradePigs");
    outputTradePigs.innerHTML = 'Trade Balance of pigs (livestock) in the world in '+sliderTradePigs.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Pigs_'+sliderTradePigs.value.toString()+'.html" ></object>';
    sliderTradePigs.oninput = function() {
      outputTradePigs.innerHTML = 'Trade Balance of pigs (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Pigs_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradePigs {
  width: 100%;
}

.sliderTradePigs {
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

.sliderTradePigs:hover {
  opacity: 1;
}

.sliderTradePigs::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradePigs::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeSoybeans" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeSoybeans">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeSoybeans" id="myRangeTradeSoybeans">
    <span id="mapTradeSoybeans"></span>
  </div>
  <script>
    var sliderTradeSoybeans = document.getElementById("myRangeTradeSoybeans");
    var outputTradeSoybeans = document.getElementById("mapTradeSoybeans");
    outputTradeSoybeans.innerHTML = 'Trade Balance of soybeans (crops) in the world in '+sliderTradeSoybeans.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Soybeans_'+sliderTradeSoybeans.value.toString()+'.html" ></object>';
    sliderTradeSoybeans.oninput = function() {
      outputTradeSoybeans.innerHTML = 'Trade Balance of soybeans (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Soybeans_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeSoybeans {
  width: 100%;
}

.sliderTradeSoybeans {
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

.sliderTradeSoybeans:hover {
  opacity: 1;
}

.sliderTradeSoybeans::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeSoybeans::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeTomatoes" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeTomatoes">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeTomatoes" id="myRangeTradeTomatoes">
    <span id="mapTradeTomatoes"></span>
  </div>
  <script>
    var sliderTradeTomatoes = document.getElementById("myRangeTradeTomatoes");
    var outputTradeTomatoes = document.getElementById("mapTradeTomatoes");
    outputTradeTomatoes.innerHTML = 'Trade Balance of tomatoes (crops) in the world in '+sliderTradeTomatoes.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes_'+sliderTradeTomatoes.value.toString()+'.html" ></object>';
    sliderTradeTomatoes.oninput = function() {
      outputTradeTomatoes.innerHTML = 'Trade Balance of tomatoes (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Tomatoes_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeTomatoes {
  width: 100%;
}

.sliderTradeTomatoes {
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

.sliderTradeTomatoes:hover {
  opacity: 1;
}

.sliderTradeTomatoes::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeTomatoes::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeTurkeys" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeTurkeys">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeTurkeys" id="myRangeTradeTurkeys">
    <span id="mapTradeTurkeys"></span>
  </div>
  <script>
    var sliderTradeTurkeys = document.getElementById("myRangeTradeTurkeys");
    var outputTradeTurkeys = document.getElementById("mapTradeTurkeys");
    outputTradeTurkeys.innerHTML = 'Trade Balance of turkeys (livestock) in the world in '+sliderTradeTurkeys.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Turkeys_'+sliderTradeTurkeys.value.toString()+'.html" ></object>';
    sliderTradeTurkeys.oninput = function() {
      outputTradeTurkeys.innerHTML = 'Trade Balance of turkeys (livestock) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Turkeys_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeTurkeys {
  width: 100%;
}

.sliderTradeTurkeys {
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

.sliderTradeTurkeys:hover {
  opacity: 1;
}

.sliderTradeTurkeys::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeTurkeys::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>
<div id="TradeWheat" class="tabcontentTrade">
  <span onclick="this.parentElement.style.display='none'" class="toprightTrade">X</span>
  <div class="slidecontainerTradeWheat">
    <input type="range" min="1970" max="2013" value="2000" class="sliderTradeWheat" id="myRangeTradeWheat">
    <span id="mapTradeWheat"></span>
  </div>
  <script>
    var sliderTradeWheat = document.getElementById("myRangeTradeWheat");
    var outputTradeWheat = document.getElementById("mapTradeWheat");
    outputTradeWheat.innerHTML = 'Trade Balance of wheat (crops) in the world in '+sliderTradeWheat.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Wheat_'+sliderTradeWheat.value.toString()+'.html" ></object>';
    sliderTradeWheat.oninput = function() {
      outputTradeWheat.innerHTML = 'Trade Balance of wheat (crops) in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/Wheat_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerTradeWheat {
  width: 100%;
}

.sliderTradeWheat {
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

.sliderTradeWheat:hover {
  opacity: 1;
}

.sliderTradeWheat::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderTradeWheat::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>

<script>
function openCityTrade(evt, cityNameTrade) {
  var iTrade, tabcontentTrade, tablinksTrade;
  tabcontentTrade = document.getElementsByClassName("tabcontentTrade");
  for (iTrade = 0; iTrade < tabcontentTrade.length; iTrade++) {
    tabcontentTrade[iTrade].style.display = "none";
  }
  tablinksTrade = document.getElementsByClassName("tablinksTrade");
  for (iTrade = 0; iTrade < tablinksTrade.length; iTrade++) {
    tablinksTrade[iTrade].className = tablinksTrade[iTrade].className.replace(" active", "");
  }
  document.getElementById(cityNameTrade).style.display = "block";
  evt.currentTarget.className += " active";
}

// Get the element with id="defaultOpenTrade" and click on it
document.getElementById("defaultOpenTrade").click();
</script>  
</div>

What other trends can we notice from the trade balances? At first sight, it might seem that for most of the features, some of the biggest global economies have **inconsistent trade balances** and thus it is surprising we can find correlations at all. Lets take pigs as an example: in 1998 France was one of the most important exporters of live pigs, whereas in 1999 it was suddenly one of the most important importers. From 2007 to 2008, we see an equally big shift for Spain. Nevertheless, this leads to an interesting observation: even though developed countries are not being consistent in the directions of their trade balance, they still tend to stay among the **most trading countries by volume**. 

<div style="float: right; width: 45%; margin: 5% 5% 5% 5%; min-width: 300px;" w3-include-html="plots/pigtradebalance.html"></div>

## Self-sufficency <a name="selfsufficiency"></a>

The self-sufficiency score is created by analyzing how much a given country **relies on external imports** of food, compared to how much they can produce for themselves. As input, we used the same features that were established as economically relevant and weighed them with their respective importance to find the **ideal self-sufficiency score**. 

$$\frac{Production \times 100}{Production + Imports – Exports}$$

### How is the self-suffiency score distributed for the selected features?

<div style="float: right; width: 100%; margin: 5% 0% 5% 0%;"> 
  <div class="slidecontainerSelfSuffiency">
    <input type="range" min="1970" max="2014" value="2000" class="sliderSelfSuffiency" id="myRangeSelfSuffiency">
    <span id="mapSelfSuffiency"></span>
  </div>
  <script>
    var sliderSelfSuffiency = document.getElementById("myRangeSelfSuffiency");
    var outputSelfSuffiency = document.getElementById("mapSelfSuffiency");
    outputSelfSuffiency.innerHTML = 'Self-sufficiency in the world in '+sliderSelfSuffiency.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/self_suf_'+sliderSelfSuffiency.value.toString()+'.html" ></object>';
    sliderSelfSuffiency.oninput = function() {
      outputSelfSuffiency.innerHTML = 'Self-sufficiency in the world in '+this.value.toString()+'\n<object style="width: 100%; height: 500px;" type="text/html" data="plots/self_suf_'+this.value.toString()+'.html" ></object>'
    }
  </script>
  <style>
.slidecontainerSelfSuffiency {
  width: 100%;
}

.sliderSelfSuffiency {
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

.sliderSelfSuffiency:hover {
  opacity: 1;
}

.sliderSelfSuffiency::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.sliderSelfSuffiency::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}
</style>
</div>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Unlike the production ranking, the self sufficiency score seems to be **rather unstable**. It is interesting to note that the countries which were by far **top producers do no stand out early on**. For instance China does not appear in the highest score until 1990. The most surprising results came from **African countries** such as South Africa, the United Republic of Tanzania, Nigeria and the Ivory Coast that constantly have a **score competing with the richest countries** which was unexpected. (***See import/export and production***). Even though the general trend tends to show that **richer countries are more independent**, there are **outliers** and the score seems to have a pretty **high variance**.

### create and add bar plot with self sufficiency for aspec year and some countries?!

### -> Comparison with GDP??

TODO **TODO**

### Link with exporters??

TODO **TODO**

## Conclusion <a name="conclusion"></a>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **China, USA, Brazil**. These are the countries that feed the world. They are the biggest producers in almost all categories. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; We observe a **strong correlation between wealth and production in general**. There is probably also a **mutual causality** between the two observations, meaning that the more you produce the wealthier you are and the wealthier you are then the more you can produce. But more interestingly, we also observe that the amount of **agricultural trade** a country engages in has an even higher positive impact on their GDP. Most of the features selected are about trade: whether its about exporting maize or importing tomatoes, being an important part of the **global interconnected economy** turns out to be postive for economic growth. In light of recent trends by especially the US to become more sceptical of global trade, it could be relevant to keep in mind what consequences might come from this. 



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Another important conclusion we make is the prominent role of **animal agriculture**. The highest valued feature is **green maize**, which is only used to **feed animals**. Many other features are **live animal imports** and or otherwise linked to crops, which are to a significant extent raised for animal food as well. It takes a lot more land, energy and ressources to produce food from animals, so it makes sense that mostly richer countries are able to afford having a diet with many animal products. 
