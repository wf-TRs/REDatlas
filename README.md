# REDatlas: Mapping the Global Distribution of Repeat Expansion Disorders

**REDatlas** is an interactive resource that visualizes the **geographic distribution** of **Repeat Expansion Disorders (REDs)** worldwide.

Explore:
- Geographic regions where REDs have been reported
- Disorder-specific repeat length thresholds from the literature
- Integrated links to [GeneReviews](https://www.ncbi.nlm.nih.gov/books/NBK1116/) and [OMIM](https://www.omim.org/)
- A Streamlit-based map interface for visual exploration

[View the Interactive Map Here](https://map-url.com)

---

## Setup & Running the App

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
pip install streamlit numpy pandas matplotlib folium requests openpyxl
```


### 2. Cloning the Repository

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/wf-TRs/REDatlas.git
cd REDatlas
```

### 3. Set Up the Database

Create and populate the SQLite database by running:

```bash
sqlite3 data.sqlite < schema.sql
python load_database.py
```

### 4. Launch the Streamlit App

Start the interactive REDatlas map with:

```bash
streamlit run final_map.py
```

You can now view your Streamlit app in your browser at: (http://localhost:8501)

### Accessing the App on a Remote Compute Cluster

If you are running the Streamlit app on a remote compute cluster, follow these steps to run the app and access it locally via SSH port forwarding:

1. **Request resources and launch the app on the cluster**

   SSH into your cluster login node, then run:

   ```bash
   salloc --time=2:00:00 --mem=4G --cpus-per-task=2  # Adjust resource request as needed
   ```
   
 Once allocated, start the Streamlit app on the compute node:
    ```bash
    streamlit run final_map.py
    ```
    
2. **Create an SSH tunnel from your local machine**

Open a new terminal on your local computer and run:

```bash
ssh -L 8501:localhost:8501 <login-node> -t ssh -L 8501:localhost:8501 <compute-node>
```

3. **Access the app in your browser**

Open your web browser and navigate to: (http://localhost:8501)


## Resources

Repeat length thresholds presented in REDatlas have been curated from:

> Indhu Shree Rajan Babu, Egor Dolzhenko, Michael A. Eberle, Jan M. Friedman. *Sequence composition changes in short tandem repeats: heterogeneity, detection, mechanisms and clinical implications*. Nature Reviews Genetics.  
> [https://pubmed.ncbi.nlm.nih.gov/38467784/](https://pubmed.ncbi.nlm.nih.gov/38467784/)

- gnomAD STR table: [https://gnomad.broadinstitute.org/short-tandem-repeats?dataset=gnomad_r3](https://gnomad.broadinstitute.org/short-tandem-repeats?dataset=gnomad_r3)
- STRchive: [https://strchive.org/loci/](https://strchive.org/loci/)
- STRipy: [https://stripy.org/database](https://stripy.org/database)
- GeneReviews: [https://www.ncbi.nlm.nih.gov/books/NBK535148/](https://www.ncbi.nlm.nih.gov/books/NBK535148/)


## Citation

If you use REDatlas in your research, please cite:

> Indhu Shree Rajan Babu, Readman Chiu, Ben Weisburd, Iris Caglayan, Heidi L. Rehm, Inanc Birol, Jan M. Friedman. Population-Level Characterization of Disease-Associated Tandem Repeat Loci in Long-Read Diploid Assemblies: Integrating Genotype, Sequence, Phylogenetic, and Local Ancestry Analyses, and Linkage Disequilibrium Structure.


## Authors

- **Iris Caglayan** — Primary developer, code author, and data curator
- **Indhu Shree Rajan Babu** — Project lead, data curation, and supervision


## Contact

For questions or collaborations, please contact:  
**Indhu Shree Rajan Babu** — [indhu.babu@bcchr.ca](mailto:indhu.babu@bcchr.ca)


## Acknowledgments

We gratefully acknowledge the following resources that made REDatlas possible:

- **Geodata:** Country boundary polygons are derived from [Natural Earth](https://www.naturalearthdata.com/), via the [datasets/geo-boundaries-world-110m](https://github.com/datasets/geo-boundaries-world-110m) GeoJSON package.  
  Licensed under the [Open Data Commons Public Domain Dedication and License (PDDL)](https://opendatacommons.org/licenses/pddl/).

We thank Natural Earth and the Open Knowledge Foundation for making this data openly available.
