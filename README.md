# PySpark Codes

A collection of PySpark and Apache Iceberg code examples and utilities for local Spark development.

## DevContainer Setup

This project uses **DevContainers** to provide a consistent Spark development environment across all platforms. The setup is based on the [local_spark_setup](https://github.com/josephmachado/local_spark_setup) repository. follow [Start Data Engineering](https://github.com/josephmachado) for more quality content.

### Prerequisites

Before setting up the devcontainer, ensure you have:

1. **Git** version >= 2.37.1 - [Install Git](https://github.com/git-guides/install-git)
2. **Docker** version >= 20.10.17 - [Install Docker](https://docs.docker.com/engine/install/)
3. **Docker Compose v2** version >= v2.10.2 - [Install Docker Compose](https://docs.docker.com/compose/#compose-v2-and-the-new-docker-compose-command)
4. **Visual Studio Code** - [Download VS Code](https://code.visualstudio.com/download)
5. A computer with at least **4GB RAM**

**Note:** You do not need to install Spark, Java, or any other dependencies directly on your computer. Everything is containerized!

### Local Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kiran73code/PySpark_codes.git
   cd PySpark_codes
   ```

2. **Open in Visual Studio Code:**
   ```bash
   code .
   ```

3. **Rebuild and Reopen in Container:**
   - Open the Command Palette: `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS)
   - Type: `Dev Containers: Rebuild and Reopen in Container`
   - VS Code will start the Docker containers and create a dev environment inside them

4. **Wait for setup to complete:**
   - VS Code will install all extensions and dependencies automatically
   - Check the `.devcontainer/devcontainer.json` for the configuration details

Your Spark development environment is now ready!

### Environment Architecture

The devcontainer spins up the following services:

- **Spark**: Master, Worker, History Server, and Thrift Server (spark-iceberg container)
- **MinIO**: S3-compatible object storage for local development
- **Iceberg REST Interface**: REST API for interacting with Iceberg tables

### Features

- ✅ Run and debug Spark interactively with Jupyter Notebooks
- ✅ Use Spark UI to explore data processing performance
- ✅ View Iceberg data and explore Parquet files with Data Wrangler
- ✅ Integrated development environment with all tools pre-configured

### Shutting Down the Environment

When done working, close the containers:
1. Click the **DevContainers** icon in the bottom-left corner of VS Code
2. Click **Close Remote Connection** or **Close Container**

## Project Structure

```
├── notebooks/              # Jupyter notebooks for interactive development
├── src/                   # Python scripts and source code
├── data/                  # Data files and datasets
├── warehouse/             # Local data warehouse (Iceberg tables)
├── localwarehouse/        # Alternative warehouse location
└── README.md             # This file
```

## PySpark Code Examples

### Getting Started

_Add your PySpark code examples here:_

- [Example 1: Basic DataFrame Operations]
- [Example 2: Data Aggregations]
- [Example 3: Working with Iceberg Tables]
- [Example 4: Advanced Transformations]

### Available Notebooks

Several Jupyter notebooks are available in the `notebooks/` directory:

- `PyIceberg - Getting Started.ipynb` - Introduction to PyIceberg
- `PyIceberg - Write support.ipynb` - Write operations with PyIceberg
- `Iceberg - An Introduction to the Iceberg Java API.ipynb` - Iceberg API overview
- `Iceberg - Getting Started.ipynb` - Basic Iceberg operations
- And more...

### Writing Your First PySpark Script

Create a new Python file in the `src/` directory:

```python
from pyspark.sql import SparkSession

# Initialize Spark Session
spark = SparkSession.builder.appName("MyApp").getOrCreate()

# Your PySpark code here
df = spark.read.csv("path/to/data.csv", header=True)
df.show()
```

Run it from within the devcontainer:

```bash
python src/your_script.py
```

## Using Jupyter Notebooks

To start Jupyter within the devcontainer:

```bash
jupyter notebook --ip=0.0.0.0 --allow-root
```

Access it at `http://localhost:8888`

## Additional Resources

- [Start Data Engineering - Local Spark Setup](https://www.startdataengineering.com/post/spark-local-setup/)
- [Apache Spark Documentation](https://spark.apache.org/docs/latest/)
- [Apache Iceberg Documentation](https://iceberg.apache.org/docs/latest/)
- [PyIceberg Documentation](https://py.iceberg.apache.org/)

## Contributing

Feel free to add more PySpark examples, utilities, and documentation to this repository.

## License

This project is inspired by and based on [josephmachado/local_spark_setup](https://github.com/josephmachado/local_spark_setup).

---

**Happy Spark Development!** 🚀
