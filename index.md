<div class="content-large"><iframe width="1200" height="675" src="https://www.youtube.com/embed/FMjuqpiuE3U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></div>

## AI-Enhanced Satellite Imagery (2016 - 2023)

In-house Machine Learning Analysis of Forestation Changes with 160GB of Satellite Data coerced from **multiple sources** (Landsat-8, Landsat-9, Sentinel-2) on **multiple bands** (RBG + Multi-Spectral).

---

## How

We broke down the visible (RBG) and non-visible (near infra-red) bands and enhanced their resolution using AI to feed into our proprietary classification and clustering  algorithm to detect land-cover and look for forestation changes.

### Introduction

Remote sensing data from satellites has revolutionized the analysis of climate change and deforestation. Satellites capture multispectral and hyperspectral data, enabling the development of geospatial models and analytical tools for detecting and monitoring environmental changes. Biophysical variables like vegetation indices, surface temperature, and precipitation, derived from remote sensing data, quantify the impact of climate change on ecosystems. Forest cover and deforestation can be monitored using remote sensing data to generate forest cover maps and track changes over time.

### Data Sources

Sentinel-2[^sentinel-2], launched in 2015 as part of the Copernicus program, is a satellite equipped with a multispectral sensor that provides high-resolution imagery and data. It has 13 spectral channels and a spatial resolution of 10-60 meters in VNIR and SWIR regions, enabling vegetation monitoring and minimizing atmospheric effects. With a 785 km orbit height, two satellites allow for repeated surveys every 5 days at the equator.

Landsat 9[^landsat-9], launched on Sep 27, 2021, is the latest addition to the Landsat program, which has been providing Earth remote sensing data since 1972. Landsat 9 and its virtual twin, Landsat 8, operate in a tandem formation, imaging the Earth's surface over 16-day periods with an 8-day phase difference. The initial on-orbit verification (OIV) period included an underfly maneuver where Landsat 9 flew underneath Landsat 8, allowing for cross-calibration of the instruments. The satellites are equipped with the same Operational Land Imagers (OLI)[^OLI-in]<sup>,</sup>[^OLI-out] with a ground sample distance of 30 meters, but OLI-2 on Landsat 9 downloads all 14 bits of image data, compared to 12 bits on OLI. Landsat 9 also has enhancements in radiometric calibration and a baffle in its Thermal Infrared Sensor (TIRS-2)[^TIRS-design]<sup>,</sup>[^TIRS-spec] to mitigate stray-light issues. The data from Landsat 9 and Landsat 8 is crucial for various geospatial and remote sensing applications, such as land use and land cover change, natural resource monitoring, and climate change assessment.

### Proposed Approach

> This study utilized a multi-layered Artificial Neural Network (ANN) with five input levels and three hidden layers. The ANN was trained on 5,000 samples and 100 trees were used for constructing model classes for the primary parameters.

The input layer of the model received geospatial and remote sensing data, which was then passed to the hidden layers. The interconnection between the layers assigned weights to each input in a random manner, which were adjusted during the training process. Bias was applied to each input neuron, and the weighted total, a combination of weights and preferences, was conveyed through the activation function. The activation function determined which node in the hidden layers should be used for feature extraction and computed the output accordingly. The model weights were updated during the training process to optimize the prediction process.

<figure class="content-medium">
  <img src="/static/img/2023RGB_low2.jpg" loading="lazy">
  <figcaption>
    Lowest forest LULC (Land Use and Land Cover) detected.
  </figcaption>
</figure>

The input data was converted into numerical form by the input nodes, with each node allocated an activation value that denoted the intensity of the action. The activation value was then transferred to the next node based on the weights and the activation function, and each node calculated and updated the weighted total using the transfer function. This process of activation occurred in each neuron, and the nodes decided whether to transmit the signal or not. The weights of the model were adjusted during the training process to determine the signal propagation across the network until it reached the destination node.

The output of the artificial neural network (ANN) was then passed to a random forest (RF) classifier. The RF approach involved randomly selecting n records from the dataset of ANN outputs, and individual decision trees were created for each sample. Each decision tree generated a result, and the simplest RF classifier with random features was created by randomly splitting a limited set of input variables at each node. The combination of the ANN and RF classifiers, referred to as ANN_RF, was found to yield the best results when using optimized hyperparameters.

<figure class="content-medium">
  <img src="/static/img/2022Soil2.jpg" loading="lazy">
  <figcaption>
    Analysis layer results of lowest forest LULC (Land Use and Land Cover) detected.
  </figcaption>
</figure>

The suggested method aimed to merge the hyperparameters of the RF and ANN classifiers, optimizing the parameters of both models to further improve the performance of the overall prediction process. This integration of geospatial, remote sensing, artificial intelligence, and machine learning techniques in the ANN_RF approach with optimized hyperparameters has the potential to enhance the accuracy and efficiency of prediction tasks in geospatial and remote sensing applications.

The study utilized a novel approach that combined neural-based and object-based methods for land use and land cover (LULC) classification. This approach, referred to as ANN_RF, accessed thousands and millions of simulated neurons in artificial neural networks (ANNs) to train the classifier. The input to the RF (Random Forest) classifier was generated through the implementation of ANN_RF in the SAGA software, using the outputs of the ANNs.

<figure class="content-medium">
  <img src="/static/img/2022RGB_High2.jpg" loading="lazy">
  <figcaption>
    Highest forest LULC (Land Use and Land Cover) detected.
  </figcaption>
</figure>

Unlike traditional RF classifiers that build a single tree, each tree in ANN_RF was built individually using packing and randomness features, resulting in a forest that was unrelated to the expectations of the individual trees. This approach was applied to LULC classification using Landsat-8 and Sentinel-2A satellite data, which were obtained for the study area before and after preprocessing, as described in detail in the following section.

<figure class="content-medium">
  <img src="/static/img/2021Green4.jpg" loading="lazy">
  <figcaption>
    Analysis layer results of highest forest LULC (Land Use and Land Cover) detected.
  </figcaption>
</figure>

The proposed classifier ANN_RF was implemented in SAGA software for LULC classification and its accuracy was assessed. A change matrix with a polygon/grid to identify LULC changes in the Imphal area near the border between India and Myanmar, with a spatial resolution of <mark>10-15 meters</mark> from Landsat-8 and Sentinel-2A satellites.

## Conclusion

The analysis of geospatial and remote sensing data reveals multiple vegetation and forestation patterns, both cyclical and non-cyclical in nature. Using advanced techniques from artificial intelligence (AI), machine learning (ML), and deep learning (DL) disciplines, the study identifies seasonal patterns showing a consistent decrease in vegetation from December to May. However, the impact of weather variations on this period is found to be inconsistent, which can be attributed to the effects of climate change.

Furthermore, the study takes into account the fluctuations in impoundment levels in the Maphou Dam reservoir, close proximity to our first Carbon Removal Nature-Based Solutions, which have been found to cause minor variations in the number of detected vegetation and forest area pixels. 

> These findings highlight the complex interactions between climate change, weather variations, and anthropogenic factors, and the importance of using advanced geospatial and remote sensing techniques to analyze and interpret such data.

The use of deep learning algorithms, such as convolutional neural networks (CNNs) and recurrent neural networks (RNNs), enables the identification and classification of vegetation and forestation patterns with high accuracy. Additionally, the study employs advanced geospatial analysis techniques, such as normalized difference vegetation index (NDVI)[^ndvi] and principal component analysis (PCA), to extract meaningful information from the remote sensing data. These findings contribute to our understanding of the complex dynamics of vegetation and forestation patterns, and provide valuable insights for monitoring and managing ecosystems in the context of climate change and human activities.

[//]: # Footnotes

[^sentinel-2]: The Copernicus [SENTINEL-2](https://sentinel.esa.int/web/sentinel/missions/sentinel-2) mission comprises a constellation of two polar-orbiting satellites placed in the same sun-synchronous orbit, phased at 180° to each other. It aims at monitoring variability in land surface conditions, and its wide swath width (290 km) and high revisit time (10 days at the equator with one satellite, and 5 days with 2 satellites under cloud-free conditions which results in 2-3 days at mid-latitudes) will support monitoring of Earth's surface changes.
[^landsat-9]: [Landsat 9](https://landsat.gsfc.nasa.gov/satellites/landsat-9/) - a partnership between NASA and the U.S. Geological Survey— continues the Landsat program’s critical role in monitoring, understanding and managing the land resources needed to sustain human life.
[^OLI-in]: The instrument level measurements of [OLI-2](https://landsat.gsfc.nasa.gov/satellites/landsat-9/landsat-9-instruments/oli-2-design/oli-2-relative-spectral-response/) were made using the Goddard Laser for Absolute Measurement of Radiance (GLAMR) facility. GLAMR consists of a system of tunable lasers that are fiber coupled to an integrating sphere, which can provide a near full field-of-view, uniform target for instrument characterization.
[^OLI-out]: The [out-of-band spectral responses](https://landsat.gsfc.nasa.gov/satellites/landsat-9/landsat-9-instruments/oli-2-design/out-band-oli-2-relative-spectral-response/) were measured at the focal plane module level, when the detectors and the filters were mated but before the modules were assembled into a signal focal plane array. Individually, the modules were put in an evacuated Dewar, cooled to operational temperature and illuminated with monochromatic light.
[^TIRS-design]: The [TIRS-2](https://landsat.gsfc.nasa.gov/satellites/landsat-9/landsat-9-instruments/tirs-2-design/) instrument is a two-band thermal imaging sensor with a push broom sensor (like OLI-2). Its focal plane has long arrays of photosensitive detectors.
[^TIRS-spec]: The instrument-level spectral measurements of [TIRS-2](https://landsat.gsfc.nasa.gov/satellites/landsat-9/landsat-9-instruments/tirs-2-design/tirs-2-relative-spectral-response/) were made using a test configuration that has been upgraded and improved since the Landsat-8 TIRS instrument-level test.
[^ndvi]: Landsat [Normalized Difference Vegetation Index](https://www.usgs.gov/landsat-missions/landsat-normalized-difference-vegetation-index) (NDVI) is used to quantify vegetation greenness and is useful in understanding vegetation density and assessing changes in plant health.