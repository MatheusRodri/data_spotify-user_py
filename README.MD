# 🎧 Spotify Data Monitor & Analytics

[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![Apache Spark](https://img.shields.io/badge/apache_spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)](https://spark.apache.org/)
[![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=Databricks&logoColor=white)](https://databricks.com/)
[![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)

## Table of Contents

- [Context](#-context)
- [Software features](#-software-features)
- [Technologies and tools](#-technologies-and-tools)
- [Architecture](#-architecture)
- [Repository structure](#-repository-structure)
- [Requirements](#-requirements)
- [How to run](#-how-to-run)
- [Autor](#-autor)

## 📌 Context 

The project is an analytical dashboard focused on processing and visualizing your extended streaming history from Spotify. It is designed to run easily in the **Databricks** environment and is extremely simple to use (focused on beginners). Just import your personal data and see the magic happen through a detailed dashboard in Power BI, which displays your most played songs, favorite artists, total listening time, and much more.

## 🚀 Software features

- **Easy Data Ingestion**: Simply place your history files in the designated folder (`extended`).
- **Automated Setup**: Environment configuration and table preparation by running a single notebook (`databricks.ipynb`).
- **Ready Data Pipeline**: Extraction and transformation (ETL) of raw data using pre-configured notebooks (bronze and silver layers).
- **Interactive Dashboard in Power BI**: Easy-to-view metrics in a Power BI template that connects directly to your data in the cloud.

## 🛠️ Technologies and tools

- **Language**: Python (PySpark and Pandas)
- **Data Platform**: Databricks
- **Visualization**: Power BI

## 📋 Architecture

1. Raw JSON files (Extended streaming history from Spotify) are provided by the user.
2. The Databricks environment processes the ingestion (Bronze layer) and transformation (Silver layer) of data via PySpark.
3. Power BI connects to the Databricks cluster using the Server (Host) and HTTP Path (Path) parameters to consume and display the final data.

## 📁 Repository structure

```text
├── data/
│   └── extended/                    # Folder where Spotify JSON files should be placed
├── notebooks/
│   ├── history/                     # ETL Notebooks (Processing)
│   │   ├── 01 - bronze_history_audio_user.ipynb
│   │   ├── 02 - silver_history_audio_user.ipynb
│   │   └── 03 - silver_history_only_audio_user.ipynb
│   └── setup/                       # Configuration notebooks
│       ├── databricks.ipynb         # Initial Databricks setup
│       └── powerbi.ipynb            # Script to capture connection data for Power BI
├── powerbi/
│   ├── dashboard_spotify.pbix       # Main Power BI dashboard file
│   └── resources/                   # Auxiliary resources and images
├── .env.exemple
├── .gitignore
└── README.MD                        # Project documentation
```

## 📦 Requirements

- Request your [Extended Streaming History from Spotify](https://www.spotify.com/account/privacy/).
- A Databricks account with an active cluster (can be the Community Edition).
- Power BI Desktop installed on your computer.

## ⚙️ How to run

1. **Get your data**: Request and download your extended streaming history from [Spotify](https://www.spotify.com/account/privacy/).
2. **Upload the project**: Upload this project (files/folders) to your Databricks workspace.
3. **Add your data**: Place the `.json` files downloaded from Spotify inside the `data/extended/` folder.
4. **Databricks Setup**: Open the `notebooks/setup/` folder and run the `databricks.ipynb` notebook to prepare the environment.
5. **Process the data**: Navigate to the `notebooks/history/` folder and run the notebooks in numerical order (01, 02, and 03).
6. **Get the credentials**: Go back to the `notebooks/setup/` folder and run the `powerbi.ipynb` notebook. It will display the **Host** and **Path** fields of your cluster.
7. **Configure the Dashboard**:
   - Open the `powerbi/dashboard_spotify.pbix` file in Power BI Desktop on your computer.
   - On the home page, click the arrow below **Transform Data** and select **Edit parameters**.
   - Enter the **Host** and **Path** values captured in the previous step.
   - Click **Apply changes**.
8. The dashboard will load your data directly from Databricks. Enjoy!

## 👤 Autor

Matheus Rodrigues 
[LinkedIn](https://www.linkedin.com/in/matheus-rodrigues-mrj/) | [GitHub](https://github.com/MatheusRodri)
