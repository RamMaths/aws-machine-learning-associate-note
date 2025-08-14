# Data Ingestion and Storage

## Data Engineering Fundamentals

### Types of Data

#### Structured Data

- Definition: Data that is orgnizied in a defined manner or schema, typically found in relational databases
- Characteristics:
    - Easily queryable
    - Organized in rows and columns
    - Has a consistent structure
- Examples:
    - Database tables
    - CSV files with consistent columns
    - Excel spread sheets

#### Unstructured Data

- Definition: Data that doesn't have a predefined structure or shcema
- Characteristics:
    - Not Easily queryable without preprocessing
    - May come in various formats
- Examples:
    - Text files without a fixed formats
    - Videos and audio files
    - Images
    - Emails and word processing documents

#### Semistructured Data

- Definition: data that is not as organized as structured data but has some level of structure in the form of tags, hierarchies, or other patterns.
- Characteristics:
    - Elements might be tagged or categorized in some way
    - More flexible than structured data but not as chaotic as unstructured data
- Examples:
    - XML and JSON files
    - Email headers (which have a mix of structured fields like date, subject, etc and unstructured data in the body )
    - Log files with varied formats

### Properties of Data

#### Volume

- Definition: Refers to the amount or size of data that organizations are dealing with at any given time.
- Characteristics:
    - May range from gigabytes to petabytes or even More.
    - Challenges in storing, processing, and analyzing high volumes of data.
- Examples:
    - A popular social media platform processing terabytes of data daily from user posts images, and videos.
    - Retailers collecting years' worth of transaction data, amounting to several petabytes.

#### Velocity

- Definition: Refers to the speed at which new data is generated, collected, and processed
- Characteristics:
    - High velocity requires real-time or near-real-time processing capabilities.
    - Rapid ingestion and processing can be critical for certain applications.
- Examples:
    - Sensor data from IoT devices Streaming readings every milisecond.
    - High-frequency trading systems where milliseconds can make a diffrence in decision-making.

#### Variety

- A business analyzing data from relational databases (structured), emails (unstructured), and JSON logs (semi-structured).
- Healthcare systems collecting data from electronic medical records, wearable, health devices, and patient feedback forms.
