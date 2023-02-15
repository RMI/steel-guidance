# Technical Specifications for RMI Steel PCF Data Exchange
## Updated 14 February 2023 

-------------------------
## 1. Introduction 

This document contains the necessary technical foundation for a steel data model extension to the [Pathfinder Network,](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network) developed by [RMI.](https://rmi.org/) For full documentation of the Pathfinder Network, refer to the link above. 

The goal of this document is to enable the interoperable exchange of steel Product Carbon Footprints, in accordance with the RMI's [Steel Emissions Reporting Guidance](https://github.com/RMI/steel-guidance/blob/main/RMI%20Horizon%20Zero%20Steel%20Guidance.pdf), across conforming host systems. 

## 2. Terminology 

For a full list of terminology, please refer to the [Terminology](https://wbcsd.github.io/data-exchange-protocol/v2/#terminology) section of the Pathfinder techical specification. 

#### Abatement Technology 
  A qualitative label of the techology used to reduce emissions in the steel supply chain. For more information please refer to the [Abatement Technology] section of RMI's [Steel Emissions Reporting Guidance.](https://github.com/RMI/steel-guidance/blob/main/RMI%20Horizon%20Zero%20Steel%20Guidance.pdf)
  
#### Credits 
  Avoided emissions outside the fixed systems boundary. Credits are required to be seperately reported from the total emissions intensity.
  
#### Process Names 
  Discrete processes used in the production of steel. E.g. hot rolling, briquetting, casting. For more information see Sec 2.2 Fixed Boundary of RMI's [Steel Emissions Reporting Guidance.](https://github.com/RMI/steel-guidance/blob/main/RMI%20Horizon%20Zero%20Steel%20Guidance.pdf)

#### Process Steps 
  A grouping of Process Names along with their total emissions intensity, recycled content, exports, credits, and other related meta-data. See [4.6. Data Type ProcessSteps](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#46-data-type-processsteps).

#### Process Groups 
  A grouping of Process Steps along with company information. See [4.4. Data Type ProcessGroups](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#44-data-type-processgroups).

## 3. Conformance 

For conformance with the Pathfinder Network, please refer to the [Conformance](https://wbcsd.github.io/data-exchange-protocol/v2/#conformance) section of the Pathfinder technical specification. 

## 4. Data Model Extension 

This section specifices a [data model extension](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-datamodelextension) for steel product footprints conforming with the [Pathfinder Network.](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network)

The data model extension contains additional information for steel products, beyond what is specified in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#data-model) 

The data model extension consists of the following: 

1. AbatementTechnology:  A qualitative label of the techology used to reduce emissions in the steel supply chain. See [Terminology](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#abatement-technology)
2. RecycledContentSet: contains information related to the total recycled content used in steel production. See [4.3 Data Type: RecycledContentSet](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#43-data-type-recycledcontentset). 
3. ProcessGroupsSet: contains information related to the companies and steps of the steel production process. See [4.5 Data Type ProcessGroupsSet](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#45-data-type-processgroupsset).

### 4.1. Data Type: AbatementTechnology 

AbatementTechnology is the enumeration of abatement technologies used in the steel production process. 
Valid values are: 

#### 4.1.1. JSON Representation 
Each AbatementTechnology MUST be encoded as a JSON string.

### 4.2. Data Type: RecycledContent

RecycledContent refers to the recycled content used in the production of the steel (see [RMI's Steel Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf))

#### 4.2.1. Properties

The properties of a RecycledContent are listed in the table below. 

| **Property**                       | **Type** | **Req** | **Specification**                                                              |
|------------------------------------|----------|---------|--------------------------------------------------------------------------------|
| recycledPercentage:<br>Percent     | Number   | M       | The percentage of recycled material <br>used in steel production               |
| postConsumerPercentage:<br>Percent | Number   | O       | The percentage of post-consumer recycled <br>material used in steel production |
| recycleName                        | String   | O       | The name of the recycling process used                                         |
| recycleDescription                 | String   | O       | A description of the recycling process used                                    |

### 4.3. Data Type: RecycledContentSet

A set of RecycledContent values. 

#### 4.3.1. JSON Representation

As an array of objects, with each object conforming to the JSON representation of RecycledContent.

### 4.4. Data Type ProcessGroups

See [Terminology](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#process-groups) section for definition of Process Groups. 

#### 4.4.1. Properties

The properties of a ProcessGroups object are listed in the table below. 

| **Property**                        | **Type** | **Req** | **Specification**                                                                                  |
|-------------------------------------|----------|---------|----------------------------------------------------------------------------------------------------|
| processCompanyNames                 | Array    | M       | An array of the companies involved in<br> discrete processes in steel production                   |
| processCompanyIds                   | Array    | M       | An array of the company ids, corresponding<br> to the processCompanyNames                          |
| processStepsSet:<br>ProcessStepsSet | Array    | M       | An array of processSteps, each containing information<br> about discrete processes in steel production  |

### 4.5. Data Type ProcessGroupsSet

A set of ProcessGroups values. 

#### 4.5.1. Properties 

As an array of objects, with each object conforming to the JSON representation of ProcessGroups.

### 4.6. Data Type ProcessSteps 

See [Terminology](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#process-steps) section for definition of Process Steps 

#### 4.6.1. Properties 

The properties of a ProcessSteps object are listed in the table below. 

| **Property**                              | **Type** | **Req** | **Specification**                                                                          |
|-------------------------------------------|----------|---------|--------------------------------------------------------------------------------------------|
| siteName                                  | String   | M       | The site name of a steel production facility                                               |
| siteIds                                   | Array    | O       | An array of the site ids, corresponding to the <br>siteName                                |
| processNamesSet:<br>processNamesSet       | Array    | M       | An array of the discrete processes, corresponding<br>to a site, in the production of steel |
| processGhgEmissions:<br>Decimal           | Number   | M       | The total GHG Emissions corresponding to the<br>discrete processes listed in processNames  |
| processPrimaryDataShare:<br>Percent       | Number   | M       | The primary data share corresponding to the <br>discrete processes listed in processNames  |
| exportProducts                            | Array    | O       | An array of export products in the production<br>of steel                                  |
| exportGhgEmissions:<br>Decimal            | Number   | O       | The total GHG Emissions corresponding to the <br>exportProducts                            |
| recycledContentSet:<br>RecycledContentSet | Array    | O       | The recycled content specific to the<br>processNames for a given processSteps object       |
| creditsSet:<br>CreditsSet                 | Array    | O       | An array of credits corresponding to the discrete<br>processes listed in processNames      |

### Data Type 4.7. ProcessStepsSet

A set of ProcessSteps values. 

#### Data Type 4.7.1. 

As an array of objects, with each object conforming to the JSON representation of ProcessSteps.

### Data Type 4.8. ProcessNames

See [Terminology](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#process-names) section for definition of Process Names. 

#### Data Type 4.8.1. JSON Representation 

Each ProcessNames value MUST be encoded as JSON string.

### Data Type 4.9. ProcessNamesSet

A set of ProcessNames of size 1 or larger.

#### Data Type 4.9.1. JSON Data Representation 

As an array of strings, with each string conforming to the JSON representation of ProcessNames.

### Data Type 4.10. Credits

See [Terminology](https://github.com/RMI/steel-guidance/blob/main/technical_specification.md#credits).

#### 4.10.1. Properties

The properties of a Credits object are listed in the table below. 

| **Property**                | **Type** | **Req** | **Specification**                                                |
|-----------------------------|----------|---------|------------------------------------------------------------------|
| creditEmissions:<br>Decimal | Number   | M       | GHG Emissions for a credit, <br>corresponding to processNamesSet |
| creditName                  | String   | M       | The name of the credit                                           |
| creditDescription           | String   | O       | A description of a given credit                                  |

### Data Type 4.11. CreditsSet

A set of Credits values. 

#### Data Type 4.11.1.

As an array of Credits, with each object conforming to the JSON representation of Credits. 
