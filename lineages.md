### Documenting Data Lineage in ISO 19115-1

A data lineage refers to the history of a dataset, detailing how it was created, transformed, and processed from its raw form to the final product. In ISO 19115-1, lineage documentation provides a traceable record that allows users to assess the trustworthiness and quality of the data by understanding each step in its journey. This is essential for transparency, reproducibility, and quality assessment in datasets, especially those used in decision-making processes.

#### Key Components of Data Lineage in ISO 19115-1

In ISO 19115-1, lineage information is captured using several key elements, which are part of the `LI_Lineage` class. These elements document both the **origin** and **transformation** of the data:


| **Element**     | **SubElement** |**Description**                                                                                   |
|-----------------|-----------------------|----------------------------------------------------------------------------|
| **LI_Lineage**  |  | Primary element for capturing lineage details, offering an overview of the dataset's history.     |
| | **statement**   | Summary of the dataset's complete lineage or processing history.                                  |
|  | **processStep** | Records each specific transformation or processing step applied to the dataset.                   |
| **LI_ProcessStep**  |                   | Defines an individual processing step, explaining actions taken to modify or generate the data.   |
|                     | **description**   | Comprehensive explanation of what was done in this step and the methods used.                     |
|                     | **rationale**     | Purpose of the process, detailing why it was necessary.                                          |
|                     | **dateTime**      | Records the exact date and time the process was carried out.                                     |
|                     | **processor**     | Identifies the person or organization responsible for performing this step.                      |
|                     | **source**        | Lists the original datasets or resources that were used in this processing step.                 |

    +-------------------+
    |    LI_Lineage     |
    +-------------------+
            |
            +---------------------------------------------+
            |                                             |
    +---------------+                            +-------------------+
    |   statement   |                            |   processStep     |
    +---------------+                            +-------------------+
                                                    |
                                                    +----------------------+
                                                    |                      |
                                            +----------------+       +------------------+
                                            |   description  |       |    rationale     |
                                            +----------------+       +------------------+
                                                    |
                                            +----------------+       +------------------+
                                            |   dateTime    |       |    processor     |
                                            +----------------+       +------------------+
                                                    |
                                            +----------------+       
                                            |     source     |
                                            +----------------+  

#### Example Structure for a Data Lineage Record

Below is an example of how a data lineage record might be documented in ISO 19115-1:

```xml
<gmd:LI_Lineage>
  <gmd:statement>
    <gco:CharacterString>Data lineage for the water quality dataset derived from satellite imagery and IoT sensor inputs.</gco:CharacterString>
  </gmd:statement>
  <gmd:processStep>
    <gmd:LI_ProcessStep>
      <gmd:description>
        <gco:CharacterString>Satellite imagery was processed to derive water quality indices for small urban lakes in Berlin.</gco:CharacterString>
      </gmd:description>
      <gmd:rationale>
        <gco:CharacterString>To create a dataset for monitoring lake water quality based on remote sensing data.</gco:CharacterString>
      </gmd:rationale>
      <gmd:dateTime>
        <gco:DateTime>2024-05-12T14:30:00</gco:DateTime>
      </gmd:dateTime>
      <gmd:processor>
        <gmd:CI_ResponsibleParty>
          <gmd:individualName>
            <gco:CharacterString>Dr. Jane Doe</gco:CharacterString>
          </gmd:individualName>
          <gmd:organisationName>
            <gco:CharacterString>Environmental Data Lab</gco:CharacterString>
          </gmd:organisationName>
          <gmd:role>
            <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/Codelist/gmxCodelists.xml#CI_RoleCode"
                              codeListValue="processor">processor</gmd:CI_RoleCode>
          </gmd:role>
        </gmd:CI_ResponsibleParty>
      </gmd:processor>
      <gmd:source>
        <gmd:LI_Source>
          <gmd:description>
            <gco:CharacterString>Sentinel-2 satellite data</gco:CharacterString>
          </gmd:description>
        </gmd:LI_Source>
      </gmd:source>
    </gmd:LI_ProcessStep>
  </gmd:processStep>
  <gmd:processStep>
    <gmd:LI_ProcessStep>
      <gmd:description>
        <gco:CharacterString>Water quality indices were refined using in-situ sensor data from KWB IoT sensors.</gco:CharacterString>
      </gmd:description>
      <gmd:rationale>
        <gco:CharacterString>To enhance the accuracy of satellite-derived water quality indices through ground truthing.</gco:CharacterString>
      </gmd:rationale>
      <gmd:dateTime>
        <gco:DateTime>2024-06-10T09:15:00</gco:DateTime>
      </gmd:dateTime>
      <gmd:processor>
        <gmd:CI_ResponsibleParty>
          <gmd:organisationName>
            <gco:CharacterString>AD4GD Project Team</gco:CharacterString>
          </gmd:organisationName>
          <gmd:role>
            <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/Codelist/gmxCodelists.xml#CI_RoleCode"
                              codeListValue="processor">processor</gmd:CI_RoleCode>
          </gmd:role>
        </gmd:CI_ResponsibleParty>
      </gmd:processor>
      <gmd:source>
        <gmd:LI_Source>
          <gmd:description>
            <gco:CharacterString>KWB IoT Sensor Data</gco:CharacterString>
          </gmd:description>
        </gmd:LI_Source>
      </gmd:source>
    </gmd:LI_ProcessStep>
  </gmd:processStep>
</gmd:LI_Lineage>
```