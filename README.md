# RMI Steel GHG Emissions Reporting Guidance
This repository holds the necessary tools and guidance for exchanging emissions data in line with RMI's Steel GHG Emissions Reporting Guidance, along with licensing and sample files.

The guidance was launched in September of 2022--you can read the blog post [here](https://rmi.org/knowing-the-emissions-of-your-steel-supply-chain/) and press release [here](https://rmi.org/press-release/rmi-releases-guidance-to-cut-steel-industrys-climate-threat/).

The guidance serves as a methodological foundation for RMI's Steel Data Model. Designed in concert with the guidance, the Steel Data Model encapsulated the outputs of the guidance, represented as a [Data Model Extension](https://wbcsd.github.io/data-model-extensions/spec/) to the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#biblio-extensions-guidance)

## Product Level Accounting Guidance
[RMI's Steel GHG Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf) provides a methodology for reporting emissions in a way that enables the development of a differentiated market for low-embodied-emissions steel that promotes the necessary investment to decarbonize the sector.

The broad outcome of the implementation of this guidance is as follows:
1. Accelerate the deployment of low-emissions steel production technologies by ensuring sufficient information is
available to link demand with supply.
2. Increase transparency and provide further information on steel production emissions with a methodology that is
consistent across geographies and commodities.
3. Enable steel consumers to purchase with a clear embodied emissions association and demonstrate evidence of that
emissions performance to their customers.
4. Credibly recognize steel producers leading their peers in terms of emissions performance, particularly in deployment
of new technologies.

This guidance was authored by [RMI](https://rmi.org/) in collaboration with the [World Business Council for Sustainable Development (WBCSD)](https://www.wbcsd.org/) and its [Automotive Partnership for Carbon Transparency (A-PACT)](https://www.wbcsd.org/Pathways/Transport-Mobility/News/Leading-manufacturers-support-move-towards-better-emissions-measurement-for-the-automotive-industry) initiative.

### Key Principles
There are four key requirements for reporting steel sector emissions using this Steel Emissions Reporting Guidance:

#### 1. Use of primary data
As much as possible, emissions calculations should be based on first-hand information from
actors in the supply chain.

#### 2. Create a boundary for comparison
Companies should report emissions against a fixed boundary (i.e., a consistent
set of processes) to enable comparability between disclosures.

#### 3. Measurement made for markets
Ensure calculation and reporting decisions provide the transparency necessary to
enable the development of a market for low-embodied-emissions products.

### Fixed System Boundary
The fixed system boundary defines all the process steps from which emissions need to be reported irrespective of the steel companies’ ownership structure. This approach solves two key issues:

#### Emissions disclosure at the corporate level will vary depending on the degree of vertical integration
#### Scope 1, 2, and 3 will likely become more fluid overtime, further limiting comparability

For more information on the Fixed System Boundary, see section 2.2 of the [accounting guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

## RMI Steel Data Model
RMI's Steel Data Model enables the use of machine-readable sharing of the product level information calculated with [RMI's Steel GHG Emissions Reporting Guidance.](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

It has been designed as an extension to the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#biblio-extensions-guidance) Extensions to the model allow for sector specific information to be added to the data model.

### Properties
RMI's Steel Data Model is comprised of the following properties:

#### Abatement Technology
  A qualitative label of the techology used to reduce emissions in the steel and aluminum supply chains. For more information, please refer to the Sec 3.4 [Abatement Technology] section of RMI's [Steel GHG Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

#### Benchmarking
  Emissions associated with all relevant processes to either crude steel or hot-rolled product. For more information see Sec 2.3 of RMI's [Steel GHG Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)
  
#### Full Boundary
  Emissions associated with all relevant processes from cradle to gate. For more information see Sec 2.2 Fixed System Boundary of RMI's [Steel GHG Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/2022/09/steel_emissions_reporting_guidance.pdf)

### Techical Guidance
For the full techical specification of RMI's Steel Data Model, see [here.](https://github.com/RMI/steel-guidance/blob/main/specs/technical_specification.md)

#### Sample and Schema Files
A sample file of the data model can be found [here.](https://github.com/RMI/steel-guidance/blob/main/samples/steel_sample.json) Note: this sample file includes the full Pathfinder Data Model file as well as RMI's Steel Data Model.

A json schema file for the data model can be found [here.](https://github.com/RMI/steel-guidance/blob/main/specs/steel_schema.json)

## Contacts

### RMI
For questions please contact ghgtransparency@rmi.org
