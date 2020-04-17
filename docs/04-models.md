

# Selected methods {#selected-methods} 

## Soil loss

In line with the AGRIBALYSE® methodology [@Koch2015], soil loss was estimated by applying the USDA RUSLE equation.

$$A = R\cdot K \cdot L \cdot S \cdot C \cdot P \cdot f$$

Where:

- *A*: computed spatial and temporal average soil loss per unit area [t·ha^-1^·yr^-1^]

- *R*: rainfall-runoff erosivity factor

- *K*: soil erodibility factor

- *L*: slope length factor

- *S*: slope steepness factor

- *C*: cover-management factor

- *P*: support practice factor

- *f*: acre to hectare conversion factor (equal to 2.47)

The AGRIBALYSE ® program computed *R* and *K* parameters according to six principal regions of France: central, north, north-east, west, south and south-west. Furthermore, climate and soil profiles were defined for each region [@Koch2015].


## Emissions of ammonia (NH~3~) to the air

In keeping with the AGRIBALYSE® methodology [@Koch2015], emissions of NH~3~ from organic fertilizers were calculated by applying the @emep-eea2009 Tier 2. While the emissions of NH~3~ resulting from the application of mineral fertilizers were calculated according to the @emep-eea2013 Tier 2, which is in line with the World Food LCA Database (WFLDB) [@nemecek2014]. This allowed to consider the effect of both temperature and soil pH in the computation of NH~3~ emissions.									
									
The NH~3~ emissions were calculated according to the following equation:
									
$$NH_3=\frac{17}{14} \cdot \sum_{m=1}^{M}(EF_a \cdot p + EF_b \cdot (1-p)) \cdot N $$

Where:

- *NH~3~*: ammonia emissions after mineral fertilizer application [kg NH~3~]

- *m*: fertilizer type (M: number of fertilizer types)

- *EF~a~*: emission factor on soils with pH ≤ 7 [kg NH~3~-N/Kg N]

- *EF~b~*: emission factor on soils with pH > 7 [kg NH~3~-N/Kg N]

- *p*: fraction of soils with pH ≤ 7 [%/100]

- *N*: fertilizer application [kg N]

- *17/14* is the conversion factor from N to NH~3~.


The above equation was simplified by considering that only one value of pH is reported for a given plot, which implies assuming that the pH is homogeneous in the studied agricultural field. In the equation below, *i* can take the values *EF~a~* or *EF~b~*, whether the pH is below or above 7.									
$$NH_3=\frac{17}{14} \cdot \sum_{m=1}^{M} EF_i \cdot N$$									
									
## Emissions of nitrogen oxides (NOx,NO,NO~2~) to the air

Nitrogen oxides result principally from the nitrification process. In line with the AGRIBALYSE® methodology [@Koch2015] and the WFLDB [@nemecek2014], the @emep-eea2009 Tier 1 was applied to calculate nitric oxide emission generated from the application of organic and mineral fertilizers. Regardless of the type of fertilizer (i.e., organic or mineral) the same emission factor is used:

- **Emission factor for NOx-N**: 0.012 kg NOx-N/kg N applied
 
Prior to the computation of NO emissions, N volatized as NH~3~ was substracted from the amount of N applied.									

In ecoinvent, nitrogen oxide emissions are calculated with respect to NO~2~. In consequence, a conversion factor of 46/14 was applied to the calculated emissions in terms of N.

## Nitrate (NO~3~^-^) leaching to ground water

@faist2009 employed a simple regression model from Willigen (2000) to calculate nitrate leaching to groundwater in the context of the *Sustainability Quick Check for Biofuels Project*. The main limitation of the SQCB-NO~3~ model is that it does not account for soil hydrological and biochemical processes. In consequence, the output of this model must be considered as an estimate of nitrate leaching. Nevertheless, the SQCB-NO~3~ model has been applied in AGRIBALYSE® [@Koch2015], WFLDB [@nemecek2014] and ecoinvent [@nemecek2011] to calculate nitrate leaching in non-European agricultural fields.

The SQCB-NO3 model was selected over the SALCA-nitrate model because the former was used by AGRIBALYSE ® to calculate nitrate leaching in vineyard fields, which is a research interest of the authors. Furthermore, this model allows to consistently compute nitrate emissions for other crops, and it facilitates updating the VBA application.

Nitrate emissions were calculated according to the following regression model [@faist2009]:

$$N=21.37 + \frac{P}{c \cdot L} \Big[0.0037 \cdot S + 0.0000601 \cdot N_{org} - 0.00362 \cdot U  \Big]$$

Where:

- *N*: quantity of nitrogen leached [kg N·ha^-1^·year^-1^]

- *P*: precipitation and watering, in mm per year

- *c*: soil clay content, in basis 100

- *L*: rooting depth, in meters

- *S*: nitrogen supply, including crop residues [kg N·ha^-1^]

- *N~org~*: quantity ot nitrogen in the soil organic matter [kg N·ha^-1^]

- *U*: nitrogen uptake [kg N·ha^-1^]

A conversion factor of 62/14 was applied to the calculated emissions of nitrate in terms of N.

## Emissions of nitrous oxide (N~2~O) to air

Nitrous oxide (N~2~O) results from nitrification and denitrification processes. The global warming potential (GWP) of N~2~O for a time horizon of 100 years is 310 times the GWP of CO~2~ [@IPCC2006].

N~2~O emissions were calculated according to the following equation [@IPCC2006]:
									
$$N_2O = \frac{44}{28} \cdot \bigg (0.01 \cdot \Big(N_{tot} + N_{cr} + \frac{14}{17} \cdot NH_3 + \frac{14}{46} \cdot NOx \Big) + 0.0075 \cdot \frac{14}{62} \cdot NO_3 \bigg)$$

Where:

- *N~2~O*: emissions of nitrous oxide [kg N~2~O·ha^-1^]

- *N~tot~*: total nitrogen in mineral and organic fertilizer [kg N·ha^-1^]

- *N~cr~*: nitrogen contained in the crop residues [kg N·ha^-1^]

- *NH~3~*: losses of nitrogen in the form of ammonia [kg NH~3~·ha^-1^]

- *NOx*: losses of nitrogen in the form of nitrogen oxides [kg NO~2~·ha^-1^]

- *NO~3~*: losses of nitrogen in the form of nitrate [kg NO~3~·ha^-1^]


## Carbon dioxide (CO~2~)  from liming and urea application

The aim of applying lime in agricultural soils is to decrease soil acidity and to improve plant development. The addition of carbonates by means of limestone or dolomite entails the dissolution of carbonate limes and the release of bicarbonate (2HCO~3~^-^). Subsequently, the bicarbonate is transformed into CO~2~ and water [@IPCC2006].

In agreement with the AGRIBALYSE® methodology [@Koch2015], the WFLDB [@nemecek2014], and ecoinvent [@nemecek2011], carbon dioxide emissions generated from the application of lime and urea were calculated according to @IPCC2006 Tier 1. The calculated emissions are based on a worst-case approach because it is considered that the total amount of carbon is released in the form of CO~2~.

CO~2~ emissions from lime application:

$$CO_2-C_{Emission}=M_{limestone} \cdot EF_{limestone} + M_{dolomite} \cdot EF_{dolomite}$$									
									
Where:

- *CO~2~-C~Emissions~*: C emissions from lime application, tonnes C·yr^-1^

- *M*: annual amount of calcic limestone or dolomite, tonnes·yr^-1^

- *EF*: emission factor, tonne of C·(tonne of limestone or dolomite)^-1^



Table: (\#tab:carbon-dioxide-ef) EF-Emission factor (kg of C·kg of product^-1^)

|Product | EF|
|--------|---|
|Limestone|0.12|
|Dolomite|0.13|
|Urea|1.57|

Finally, a factor of 44/12 is applied to transform the emissions in terms of carbon into emissions based on carbon dioxide.

$$CO_2= \frac{44}{12} \cdot CO_2-C_{Emission}$$



									
## Phosphorus emissions {#phosphorous-emissions}

In agreement with the AGRIBALYSE® methodology [@Koch2015], the WFLDB methodology [@nemecek2014] and the ecoinvent methodology [@nemecek2011], emissions of phosphorous to water were calculated by applying the SALCA-P model [@prasuhn2006]. 

The SALCA-P model computes three types of emissions to water according to the mechanism generating them: 

* Phosphorus to river (emission by soil loss)
* Phosphate to ground water (emission by leaching).	
* Phosphate to river (emission by run-off)
								
									

### Phosphorus to river (emission by soil loss)

Emissions of phosphorus by soil loss were calculated according to the following equation [@prasuhn2006]:

$$P_E=A \cdot P_S \cdot F_R \cdot F_{SR} \cdot t$$
Where:

- *P~E~*: phosphorus emitted by soil loss to rivers [kg.ha^-1^.yr^-1^]

- *A*: quantity of soil lost [kg.ha^-1^.yr^-1^]

- *t*: land occupation time (number of days/365)

Table: (\#tab:phosphorous-river) Parameters for calculating phosphorous emissions to river [@prasuhn2006]

|Parameter|Definition|Default value|Units|
|---------|----------|-------------|-----|
|*P~S~*       |Phosphorous content in the upper part of the soil|0.00095|kg P·kg soil^-1^|
|*F~R~*       |Eroded particle enrichment factor|1.86|-|
|*F~SR~*      |Fraction of soil lost that reaches the river|0.2|-|


### Phosphate to ground water (emission by leaching)

Leaching of phosphate to ground water was calculated according to the following equation [@prasuhn2006]:

$$P_L=P_{LM} \cdot F_{CSS} \cdot t$$

Where:

- *P~L~*: leached phosphorus [kg.ha^-1^.yr^-1^]

- *P~LM~*: average quantity of phosphorus leached depending on the land occupation category [kg P.ha^-1^.yr^-1^]

- *F~CSS~*: correction factor for fertilization with slurry and/or sludge (see equation below)

- *t*: occupation time (number of days/365)

A conversion factor of 95/31 was applied to convert emissions of phosphorus into emissions of phosphate.

$$F_{CSS}=1+ \frac{0.2 \cdot (P_2O_{5-slurry\: and\: sludge})}{80}$$

### Phosphate to river (emission by run-off)

Emissions of phosphate to river by run-off were calculated according to the following equation [@prasuhn2006]:

$$P_R=P_{RM} \cdot F_C \cdot F_S \cdot t$$

Where:

- *P~R~*: phosphorus lost by run-off to the rivers [kg.ha^-1^.yr^-1^]

- *P~RM~*: average quantity of phosphorus lost by run-off depending on the land occupation category [kg P.ha^-1^.yr^-1^]									
									
- *F~C~*: correction factor for the form of phosphorus applied (mineral, liquid/solid organic)

- *F~S~*: slope factor. F~S~ = 0 if slope < 3%, F~S~= 1, otherwise.

- *t*: occupation time (number of days/365)

$$F_C=1+ \frac{0.7 \cdot P_2O_{5-slurry\: and \: sludge} + 0.2 \cdot P_2O_{5-mineral \: fertilizer} + 0.4  \cdot P_2O_{5-manure\: and\: compost}}{80}$$

A conversion factor of 95/31 was applied to convert emissions of phosphorus into emissions of phosphate.



## Heavy metal emissions to agricultural soil, surface water and ground water

Emissions of heavy metals to soil, ground and surface water are calculated based on a mass balance. The inputs considered are seeds, fertilizers, soil amendments, metal-based pesticides and air deposition. The outputs correspond to the emissions of trace metals into ground and surface water and the products harvested.

### Heavy metal emissions to agricultural soils

The mass balance of trace metal *(TM) x* in soil is calculated according to the following equation [@Koch2015]:

$$\Delta F_{TMx}=\sum_{SFPI_y}IN_y \cdot C_{y,x} - \Big (\sum_{PLR_z} OUT_z \cdot C_{z,x} \Big) \cdot Alloc_x \quad \forall x \in \{Cd,Cu,Zn,Pb,Ni,Cr,Hg\}$$

Where:

- *ΔFTMx*: Flow into the soil of *Trace Metal x (TMx)*

- *INy*: Quantity of input *SFPIy* containing TMx:

  + Seed

  + Fertilizer (mineral, organic, farm, sludge)

  + Pesticides

  + Sundry Inputs
 

- *Cy,x*: Content of *TMx* in input *SFPIy*

- *OUTz*: Quantity of output *PLRz* carrying the trace metal *TMx*

  + Products harvested (including co-products and/or residues exported)

  + Leaching to groundwater

  + Run-off to surface water by soil loss

- *Cz,x*: Content of *TMx* in output PLRz

- *Alloc~x~*: Allocation factor for TMx output flow. This allocation factor only takes account of part of the output flows from the deposition of trace metals. The allocation is calculated for each trace metal:

$$Alloc_x = \frac{ \sum_{SFPIy}IN_y \cdot T_{y,x}}{ \sum_{SFPIy} IN_y \cdot T_{y,x} + Dep_x}$$

### Heavy metal emissions to river

Trace metal emissions through erosion are calculated according to the following equation [@Koch2015]:

$$M_{erosion,TMx} = A \cdot S_{TMx} \cdot F_R \cdot F_{SR} \cdot t \cdot Alloc_x$$

Where:

- *M~erosion,TM~x*: emission of trace metal x to river [kg·ha^-1^·yr^-1^]

- *A*: amount of soil lost [kg·ha^-1^·yr^-1^]

- *S~TMx~*: the content of trace metal x in the upper part of the soil

- *F~R~*: eroded particle enrichment factor

- *F~SR~*: fraction of soil lost which reaches the river

- *t*: land occupation time (number of days/365)

- *Alloc~x~*: allocation factor for trace metal x

The amount of soil lost was calculated by applying the RUSLE equation. An average concentration of trace metals depending on the soil use was considered. The eroded particle enrichment factor and the fraction of soil lost that reaches the river took the default values considered in the AGRIBALYSE® methodology [@Koch2015]. Please refer to [Section](#phosphorous-emissions) \@ref(phosphorous-emissions) to retrieve the last two parameters.


### Heavy metal emissions to ground water

Trace metal emissions into ground water were calculated according to the following equation [@Koch2015]:

$$M_{leachng,TMx} = m_{leaching,TMx} \cdot Alloc_x$$

Where:

- *M~leaching,TMx~*: emission of trace metal x to ground water [kg·ha^-1^·yr^-1^]

- *m~leaching,TMx~*: average emission of trace metal x to ground water [kg·ha^-1^·yr^-1^]

- *Alloc~x~*: allocation factor for trace metal x.





									
									
									
									

  








									

									
									
								

								
																	
									
									
									
									
									

									
									
									
									

									
									
									
									


									
									

