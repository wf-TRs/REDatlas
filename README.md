# 🧬 REDatlas: Mapping the Global Distribution of Repeat Expansion Disorders

**REDatlas** is an interactive resource that visualizes the **geographic distribution** of **Repeat Expansion Disorders (REDs)** worldwide. This tool aggregates reported cases from the literature, links each disorder to relevant clinical and genomic resources, and displays population-level patterns through a user-friendly map interface.

Explore:
- 📍 Geographic regions where REDs have been reported
- 📏 Disorder-specific repeat length thresholds from the literature
- 🔗 Integrated links to [GeneReviews](https://www.ncbi.nlm.nih.gov/books/NBK1116/) and [OMIM](https://www.omim.org/)
- 💡 A Streamlit-based map interface for visual exploration

[🌐 View the Interactive Map Here](https://map-url.com)

---

## ⚙️ Setup & Running the App

### 1. Install Requirements

### Dependencies

REDatlas requires the following:

- Python 3.7+
- Streamlit
- NumPy
- Pandas
- Matplotlib
- SQLite3 (usually included with Python)
- Folium
- Requests
- openpyxl

Install dependencies using:

```bash
pip install streamlit numpy pandas matplotlib

### 2. Set Up the Database

To create and populate the local SQLite database, run the following commands:

```bash
sqlite3 data.sqlite < schema.sql
python load_database.py

### 3. Launch the Streamlit App
To run the interactive REDatlas map:

```bash
streamlit run final_map.py

Data Sources
Repeat thresholds:
