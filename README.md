# Technical Specifications for RMI Steel PCF Data Exchange
## Living document, 2 February 2023 

### Contacts

#### RMI
Lachlan Wright (lwright@rmi.org)<br>
Xiyuan Liu (xliu@rmi.org)<br>
Iris Wu (iwu@rmi.org)<br>
Sravan Chalasani (schalasani@rmi.org)

------------------------

## Abstract 

This repository holds RMI's Steel Emissions Reporting Guidance, along with licensing and related documents. The guidance was launched in September of 2022--you can read the blog post [here](https://rmi.org/knowing-the-emissions-of-your-steel-supply-chain/) and press release [here](https://rmi.org/press-release/rmi-releases-guidance-to-cut-steel-industrys-climate-threat/).

The guidance was authored by [RMI](https://rmi.org/) in collaboration with the [World Business Council for Sustainable Development (WBCSD)](https://www.wbcsd.org/) and its [Automotive Partnership for Carbon Transparency (A-PACT)](https://www.wbcsd.org/Pathways/Transport-Mobility/News/Leading-manufacturers-support-move-towards-better-emissions-measurement-for-the-automotive-industry) initiative.

-------------------------
## 1. Introduction 

This document contains the necessary technical foundation for a steel data model extension to the [Pathfinder Network,](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network) developed by [RMI.](https://rmi.org/) For full documentation of the Pathfinder Network, refer to the link above. 

The goal of this document is to enable the interoperable exchange of steel Product Carbon Footprints, in accordance with the RMI Steel Emissions Reporting Guidance, across conforming host systems. 

## 2. Terminology 


## 3. Conformance 

As well as sections marked as non-normative, all authoring guidelines, diagrams, examples, and notes in this specification are non-normative. Everything else in this specification is normative.

The key words MAY, MUST, MUST NOT, OPTIONAL, RECOMMENDED, REQUIRED, SHOULD, and SHOULD NOT in this document are to be interpreted as described in [RFC2119] [RFC8174] when, and only when, they appear in all capitals, as shown here.

A conforming host system is any algorithm realized as software and/or hardware that complies with the relevant normative statements in § 6 HTTP REST API.

A conforming requesting data recipient is any algorithm realized as software and/or hardware that complies with the relevant normative statements in § 6 HTTP REST API.

## 4. Data Model Extension 

This section specifices a [data model extension](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-datamodelextension) for steel product footprints conforming with the [Pathfinder Network.](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network)

The data model extension contains additional information for steel products, beyond what is specified in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#data-model) 

The data model extension consists of the following: 

1. AbatementTechnology 
2. RecycledContentSet 
3. ProcessGroupsSet 

### 4.1 Data Type: AbatementTechnology 

AbatementTechnology is the enumeration of abatement technologies used in the steel production process. 
Valid values are: 

#### 4.1.1 JSON Representation 
Each AbatementTechnology MUST be encoded as a JSON string.

### 4.2 Data Type: RecycledContent

RecycledContent refers to the overall recycled content used in the production of the steel (see [RMI's Steel Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

#### 4.2.1 Properties


### 4.3 Data Type ProcessGroups

#### 4.3.1 Properties


### 4.4 Data Type ProcessSteps 

#### 4.4.1 Properties 



