# Technical Specifications for RMI Aluminum PCF Data Exchange
## Updated 15 August 2023

-------------------------
## 1. Introduction
This document contains the necessary technical foundation for an aluminum data model extension to the [Pathfinder Network,](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network) developed by [RMI.](https://rmi.org/) For full documentation of the Pathfinder Network, refer to the link above.

The goal of this document is to enable the interoperable exchange of steel Product Carbon Footprints, in accordance with the RMI's
[Steel GHG Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)
, across conforming host systems.

## 2. Terminology
For a full list of terminology, please refer to the [Terminology](https://wbcsd.github.io/data-exchange-protocol/v2/#terminology) section of the Pathfinder techical specification.

### Abatement Technology
  A qualitative label of the techology used to reduce emissions in the steel and aluminum supply chains. For more information, please refer to the Sec 3.4 [Abatement Technology] section of RMI's [Steel GHG Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

### Benchmarking
  Emissions associated with all relevant processes to either crude steel or hot-rolled product. For more information see Sec 2.3 of RMI's [Steel GHG Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)
  
### Full Boundary
  Emissions associated with all relevant processes from cradle to gate. For more information see Sec 2.2 Fixed System Boundary of RMI's [Steel GHG Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)
## 3. Conformance
For conformance with the Pathfinder Network, please refer to the [Conformance](https://wbcsd.github.io/data-exchange-protocol/v2/#conformance) section of the Pathfinder technical specification.

## 4. Data Model Extension
This section specifices a [data model extension](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-datamodelextension) for steel product footprints conforming with the [Pathfinder Network.](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network)

The data model extension contains additional information for aluminum products, beyond what is specified in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#data-model)

The data model extension consists of the following:

1. Abatement Technology: A qualitative label of the techology used to reduce emissions in the steel and aluminum supply chains.
2. BenchmarkingFootprint: Contains information related to the benchmarking boundary.
3. FullFootprint: Contains information related to the full boundary.

### 4.1. Data Type: AbatementTechnology
AbatementTechnology is the enumeration of low-carbon or abatement technologies used in the steel production process.

#### 4.1.1. JSON Representation
Each AbatementTechnology must be represented as a string.

### 4.2. Data Type: BenchmarkingFootprint
Contains information related to the benchmarking boundary.

#### 4.2.1. Properties
The properties of a BenchmarkingFootprint are listed in the table below.

| **Property**                           | **Type**  | **Req** | **Specification**                                                                                                                     |
|----------------------------------------|-----------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| referencePeriodStart                   | date-time | O       | Start date-time for the full boundary footprint calculation                                                                           |
| referencePeriodEnd                     | date-time | O       | End date-time for the full boundary footprint calculation                                                                             |
| productDescription                     | String    | O       | The free-form description of the product plus other<br>information related to it such as production technology or packaging           |
| productAmount                          | Number    | O       | The unit of analysis of the product                                                                                                   |
| productDeclaredUnit                    | String    | O       | The amount of productDeclaredUnits contained within the product                                                                       |
| benchmarkingGhgEmissions               | Number    | M       | The overall emissions footprint for the aluminum product as per the<br>full reporting boundary, in ton CO2e per ton of aluminum semis |
| creditGhgEmissions                     | Number    | O       | Emissions associated with exported intermediate products                                                                              |
| scrapBasedShare:<br>Percent            | Number    | M       | The percentage of scrap used in the production of the product                                                                         |
| postConsumerscrapBasedShare:<br>Percent| Number    | O       | The percentage of post-consumer scrap used in the production of the product                                                           |
| geographyCountrySubdivision            | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |
| geographyCountry:<br>_ISO3166CC_       | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |
| geographyRegionOrSubregion             | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |

### 4.3. Data Type: FullBoundary
A geographical field for the ore-based or mine-to-smelter portion of the aluminum production. The requirements for this field corresponds to the GeographyCountry field in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)

#### 4.3.1. Properties
The properties of a FullBoundary are listed in the table below.

| **Property**                     | **Type**  | **Req** | **Specification**                                                                                                                     |
|----------------------------------|-----------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| referencePeriodStart             | date-time | O       | Start date-time for the full boundary footprint calculation                                                                           |
| referencePeriodEnd               | date-time | O       | End date-time for the full boundary footprint calculation                                                                             |
| productDescription               | String    | O       | The free-form description of the product plus other<br>information related to it such as production technology or packaging.          |
| productAmount                    | Number    | O       | The unit of analysis of the product                                                                                                   |
| productDeclaredUnit              | String    | O       | The amount of productDeclaredUnits contained within the product                                                                       |
| fullBoundaryGhgEmissions         | Number    | M       | The overall emissions footprint for the aluminum product as per the<br>full reporting boundary, in ton CO2e per ton of aluminum semis |
| geographyCountrySubdivision      | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |
| geographyCountry:<br>_ISO3166CC_ | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |
| geographyRegionOrSubregion       | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                         |

