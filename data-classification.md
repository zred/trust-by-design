## Personal Data Classifications

### PII (Personally Identifiable Information)
Direct identifiers that can pinpoint a specific individual:
* Name, email address, phone number, physical address
* VIN (Vehicle Identification Number) when linked to owner information
* Driver's license number
* Social Security Number
* Payment card information (falls under PCI-DSS scope)
* Service records containing customer names

### NPI (Non-Public Information)
A broader category that encompasses PII plus any private information not publicly available:
* Credit reports and scores used for vehicle financing
* Insurance policy details
* Financial account information
* Private communications between customers and service advisors (emails, texts)
* Internal customer notes and preferences

*Note: Often regulated under GLBA (Gramm-Leach-Bliley Act) for financial institutions*

### Confidential Data
Proprietary business information requiring protection:
* Customer contracts and pricing agreements
* Warranty claim details
* Service pricing structures
* Customer lifetime value calculations
* Negotiated fleet rates
* Internal business strategies

### Trade Secrets
Proprietary information that provides competitive advantage:
* Customer retention algorithms
* Predictive maintenance models
* Proprietary diagnostic procedures
* Marketing campaign performance data
* Customer segmentation methodologies
* Dealer cost structures

### De-identified/Decorrelated Personal Information
Data where direct identifiers have been removed or encrypted:
* Aggregate service statistics (e.g., "500 oil changes performed last quarter")
* Anonymized vehicle maintenance patterns
* Geographic trends without specific addresses
* Age ranges instead of birth dates
* Zip codes only (without full addresses)

*Warning: This data can become re-identifiable when combined with other data sources*

### Pseudonymized Data
PII replaced with artificial identifiers (tokens or hashes):
* Customer ID numbers replacing names
* Hashed email addresses for matching purposes
* Encrypted VINs

*Note: Can be re-linked to individuals with the appropriate key, therefore still requires protection*

## Data Source Classifications

### First-Party Data (1P)
Information collected directly from your customers through:
* Service appointments and check-ins
* Website forms and online booking systems
* Direct customer interactions
* Service history in your DMS/CRM systems
* Loyalty program participation
* Direct email and SMS communications

**Safe Harbor Considerations:** You have a direct consent relationship and maintain control

### Second-Party Data (2P)
Another organization's first-party data shared through partnership:
* OEM (Original Equipment Manufacturer) sharing customer data with dealership service centers
* Co-marketing partner data exchanges
* Franchise network shared customer insights

**Safe Harbor Considerations:** Requires data sharing agreements and mutual consent validation

### Third-Party Data (3P)
Data purchased or acquired from external data brokers:
* Marketing lists from data aggregators
* Behavioral and demographic overlays
* Credit bureau information
* Publicly available data compilations

**Safe Harbor Considerations:** Higher risk profile; must verify vendor compliance and lawful collection methods

### Zero-Party Data
Information customers intentionally and proactively share:
* Explicitly stated service preferences
* Vehicle maintenance goals
* Communication channel preferences
* Self-reported driving habits

**Safe Harbor Considerations:** Provides the strongest consent foundation due to clearly intentional sharing

## Safe Harbor Best Practices by Classification Level

### High Protection Requirements (PII, NPI, Trade Secrets)
* Implement encryption at rest and in transit
* Maintain strict access controls with comprehensive audit logs
* Require explicit opt-in consent for marketing use
* Conduct regular security assessments
* Establish clear breach notification procedures

### Medium Protection Requirements (Confidential Data, De-identified Data)
* Apply standard security measures
* Implement role-based access restrictions
* Establish contractual protections with vendors
* Regularly review de-identification effectiveness
* Monitor for potential re-identification risks

### Lower Protection Requirements (Anonymized Data, Public Information)
* Maintain basic security hygiene
* Ensure transparency about data usage
* Apply aggregation thresholds to prevent re-identification
* Document data handling procedures
* Regular review of classification accuracy
