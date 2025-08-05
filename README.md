# B2B Data Exchange Automation: An EDI Simulation Project

## Overview

This project simulates a real-world B2B Electronic Data Interchange (EDI) integration scenario within the transportation and logistics industry. The aim is to demonstrate the process of automating critical business document exchanges between a carrier and a shipper, highlighting the efficiencies gained by replacing manual processes with structured EDI.

Using BlueSeer's open-source ERP/EDI software, I've designed and implemented fictional EDI maps and generated simulated transaction sets (EDI X12 204, 990, 214, 210). This hands-on project offers insight into the technical aspects of EDI integration, including data mapping, document generation, and the overall flow of B2B communication in a managed service environment.

**Key Objectives:**
* To understand and apply the principles of EDI mapping for common transportation transaction sets.
* To simulate the transformation of internal flat file data into standardized EDI X12 formats.
* To illustrate the operational benefits of automated B2B data exchange, such as reduced manual errors, improved speed, and enhanced trading partner relationships.

## Setup Instructions

To explore and replicate this project, you will need the BlueSeer ERP/EDI software.

1.  **Download BlueSeer:**
    * Visit the official BlueSeer website: [https://www.blueseer.com/](https://www.blueseer.com/)
    * Download and install the appropriate version for your operating system (Windows, Linux). Follow their installation instructions carefully.

2.  **Familiarize Yourself with BlueSeer's EDI Module:**
    * After installation, launch BlueSeer.
    * Navigate to the `EDI / API` section. Explore the `Map Maintenance` and `EDI Document` sections to understand how mappings are created and documents are processed.

3.  **Load Project Files:**
    * **Data Sources:** Review the `.csv` files in the `data_sources/` directory. These represent the fictional internal data that would be used as input for EDI generation.
    * **BlueSeer Maps:** Due to the proprietary nature of BlueSeer's internal map formats, actual exportable map files are not directly included in a universally viewable format. However, detailed descriptions and screenshots of the mapping logic are provided in the `blueseer_maps/` directory to illustrate the mapping process. You would recreate these mappings manually within your BlueSeer instance.
    * **Generated EDI:** The `generated_edi/` directory contains the output EDI X12 files. You can open these in any text editor to review the structured EDI data.

4.  **Recreate Mappings (Recommended Hands-On Practice):**
    * Using the `data_sources/` files and the descriptions/screenshots in `blueseer_maps/`, attempt to recreate the EDI maps within your BlueSeer installation. This is the most valuable part of the hands-on experience.
    * Once maps are created, use the `EDI Document` generation feature in BlueSeer to process the `data_sources/` files and generate your own `generated_edi/` output. Compare your output with the samples provided.

## Project Structure and Explanation of Files

This repository is organized to logically represent the flow of an EDI integration project.

* ### `data_sources/`
    * **Purpose:** Contains sample flat files (e.g., CSV) that represent the internal business data that a carrier's ERP or TMS (Transportation Management System) would generate or consume. This simulates the raw data before it's converted to EDI.
    * **Files:**
        * `globex_204_inbound_data.csv`: Fictional data representing a Load Tender (EDI 204) sent from a shipper (RetailCo Warehouse) to the carrier (Globex Logistics Corp.). This would be data that Globex's system would receive, potentially from an external EDI service, and then need to process internally.
        * `globex_990_outbound_data.csv`: Fictional data for Globex's response (Load Tender Response - EDI 990) back to RetailCo, indicating acceptance or rejection.
        * `globex_214_outbound_data.csv`: Fictional data for Shipment Status Messages (EDI 214) from Globex to RetailCo, detailing shipment progress (picked up, in transit, delivered).
        * `globex_210_outbound_data.csv`: Fictional data for the Motor Carrier Freight Details and Invoice (EDI 210) sent from Globex to RetailCo after delivery.

* ### `blueseer_maps/`
    * **Purpose:** This directory would contain detailed documentation or screenshots of the EDI mapping configurations created within BlueSeer. BlueSeer maps are typically stored internally or require specific export functions.
    * **Content:**
        * `edi_204_mapping_overview.png` (or `.md`): Visual/textual breakdown of how internal fields map to EDI X12 204 segments (e.g., ST, B2, L11, G62, S5).
        * `edi_990_mapping_overview.png` (or `.md`): Visual/textual breakdown of mapping to EDI X12 990 segments (e.g., ST, BSN, RFT, N1).
        * `edi_214_mapping_overview.png` (or `.md`): Visual/textual breakdown of mapping to EDI X12 214 segments (e.g., ST, B10, MS1, L11, AT8, REF, PER, N1, G62).
        * `edi_210_mapping_overview.png` (or `.md`): Visual/textual breakdown of mapping to EDI X12 210 segments (e.g., ST, B3, C3, ITD, L11, G62, R3, H3, N1, L0, L1).
    * **Note:** The actual BlueSeer map files often require BlueSeer to open. Providing clear descriptions and screenshots serves as excellent documentation of the mapping logic.

* ### `generated_edi/`
    * **Purpose:** Stores the simulated EDI X12 documents generated by BlueSeer after applying the mapping logic to the `data_sources`. These are the final, standardized EDI files.
    * **Files:**
        * `sample_edi_204_tender.edi`: A sample EDI 204 document for a load tender.
        * `sample_edi_990_response.edi`: A sample EDI 990 document responding to the load tender.
        * `sample_edi_214_status.edi`: A sample EDI 214 document showing shipment status updates.
        * `sample_edi_210_invoice.edi`: A sample EDI 210 document representing the freight invoice.
    * **Note:** These files are plain text and can be opened in any text editor.

* ### `documentation/`
    * **Purpose:** Provides supplementary information, including the fictional scenario details and an overview of the EDI X12 standards used.
    * **Files:**
        * `scenario_details.md`: Describes the fictional companies ("Globex Logistics Corp." and "RetailCo Warehouse") and the typical daily workflow being simulated.
        * `edi_x12_standards_brief.md`: A brief explanation of each X12 transaction set (204, 990, 214, 210) used in this project, outlining their purpose and key segments.

---

This structured project with its `README.md` will clearly communicate your technical skills and business understanding to potential employers. Remember to populate these directories with actual files and relevant content from your BlueSeer experiments!
