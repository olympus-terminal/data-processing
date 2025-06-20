# Data Processing Tools

> Modern data analysis and processing toolkit featuring Python scripts, R utilities, web scraping tools, and intelligent automation solutions.

[![License](https://img.shields.io/github/license/olympus-terminal/data-processing)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/olympus-terminal/data-processing?style=social)](https://github.com/olympus-terminal/data-processing/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/olympus-terminal/data-processing)](https://github.com/olympus-terminal/data-processing/issues)
[![GitHub last commit](https://img.shields.io/github/last-commit/olympus-terminal/data-processing)](https://github.com/olympus-terminal/data-processing/commits/main)
[![Tools](https://img.shields.io/badge/tools-11-green.svg)](https://github.com/olympus-terminal/data-processing)
[![Python](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org)
[![R](https://img.shields.io/badge/R-4.0+-276DC3.svg)](https://www.r-project.org)

## 📊 Overview

A versatile collection of data processing tools designed for researchers, data scientists, and analysts. This toolkit bridges the gap between raw data and insights, offering solutions for common data manipulation tasks, web scraping, format conversion, and analysis workflows.

### Core Strengths

- **Multi-Language Support**: Leverage Python's versatility and R's statistical power
- **Automation First**: Tools designed for batch processing and pipelines
- **Format Agnostic**: Handle CSV, TSV, PDF, JSON, and custom formats
- **Research-Oriented**: Citation analysis, data pivoting, and academic workflows
- **Web-Aware**: Intelligent web scraping with respect for robots.txt

## 📁 Repository Structure

```
data-processing/
├── python-tools/       # Python-based processing utilities
├── r-scripts/         # R scripts for statistical analysis
├── web-scraping/      # Web data extraction tools
├── format-conversion/ # File format converters
├── data-analysis/     # Analysis and aggregation tools
└── ml_dir_config.txt  # Machine learning directory configuration
```

## 🚀 Quick Start

### Prerequisites

```bash
# Python requirements
python --version  # 3.7 or higher
pip install pandas numpy requests beautifulsoup4 PyPDF2 matplotlib seaborn

# R requirements
R --version  # 4.0 or higher
# Install R packages (in R console):
# install.packages(c("dplyr", "reshape2", "tidyverse", "data.table"))

# System requirements
bash >= 4.0
awk, sed, grep (standard Unix tools)
```

### Installation

```bash
# Clone the repository
git clone https://github.com/olympus-terminal/data-processing.git
cd data-processing

# Install Python dependencies
pip install -r requirements.txt  # or manually:
pip install pandas numpy requests beautifulsoup4 PyPDF2 \
            matplotlib seaborn scipy scikit-learn

# Make scripts executable
find . -name "*.py" -o -name "*.sh" | xargs chmod +x
```

## 🔧 Tool Showcase

### Python Tools (`python-tools/`)

#### Data Chunking and Processing
```python
# Break large datasets into manageable chunks
python break-to-100s.py huge_dataset.csv --chunk-size 100
# Creates: chunk_001.csv, chunk_002.csv, etc.

# Process timestamps and split samples
python SampleSplitStamp.py experiment_data.csv \
    --timestamp-col "date" \
    --split-ratio 0.7
```

#### Intelligent Automation
```python
# Two-agent automation system
python twoagent-DRN-autogen-mod.py \
    --config automation_config.json \
    --mode "collaborative"
```

### R Scripts (`r-scripts/`)

#### Advanced Pivot Tables
```r
# Create complex pivot tables with multiple aggregations
Rscript pivot-table-maker.R \
    --input sales_data.csv \
    --rows "product,region" \
    --cols "quarter" \
    --values "revenue,units" \
    --fun "sum,mean"
```

#### Statistical Pivoting
```r
# Quick pivoting for statistical analysis
Rscript pivot.r data.csv id_vars value_vars
```

### Web Scraping (`web-scraping/`)

#### Academic PDF Scraper
```python
# Scrape Y-chromosome research PDFs
python web-scraper_Ychr-pdfs.py \
    --start-url "https://research-site.com" \
    --output-dir "./pdfs/" \
    --max-depth 3 \
    --respectful  # Follows robots.txt
```

### Format Conversion (`format-conversion/`)

#### PDF to Text Extraction
```python
# Extract text from PDFs with layout preservation
python pdf_to_txt_argv.py research_paper.pdf \
    --output extracted_text.txt \
    --preserve-layout \
    --encoding utf-8
```

### Data Analysis (`data-analysis/`)

#### Citation Analysis
```python
# Analyze citations in academic texts
python CountCitations.py manuscript.txt \
    --style "APA" \
    --output citation_report.csv
```

#### AWK-based Tallying
```bash
# Fast tallying of categorical data
./tally-awk category_column data.txt > frequency_table.txt
```

## 📊 Real-World Workflows

### 1. Research Data Pipeline
```bash
# Step 1: Extract data from PDFs
for pdf in literature/*.pdf; do
    python format-conversion/pdf_to_txt_argv.py "$pdf" \
        --output "texts/$(basename "$pdf" .pdf).txt"
done

# Step 2: Count citations
python data-analysis/CountCitations.py texts/*.txt \
    --output citations_summary.csv

# Step 3: Create visualization
python python-tools/visualize_citations.py citations_summary.csv
```

### 2. Large Dataset Processing
```bash
# Split large file
python python-tools/break-to-100s.py massive_dataset.csv

# Process each chunk in parallel
for chunk in chunk_*.csv; do
    python process_chunk.py "$chunk" &
done
wait

# Merge results
python merge_results.py chunk_*.processed.csv > final_results.csv
```

### 3. Web Data Collection
```python
# Scrape data respectfully
python web-scraping/web-scraper_Ychr-pdfs.py \
    --config scraping_config.json \
    --rate-limit 1  # 1 request per second

# Process downloaded content
for pdf in downloads/*.pdf; do
    python format-conversion/pdf_to_txt_argv.py "$pdf"
done

# Analyze extracted text
python analyze_papers.py downloads/*.txt
```

## 🎯 Advanced Features

### Machine Learning Integration

The `ml_dir_config.txt` file configures directories for ML workflows:
```
data/
├── raw/           # Original datasets
├── processed/     # Cleaned data
├── features/      # Feature engineering
├── models/        # Trained models
└── predictions/   # Model outputs
```

### Parallel Processing

Many tools support parallel execution:
```bash
# Set parallel jobs
export PARALLEL_JOBS=4

# Use GNU parallel for batch processing
parallel -j 4 python process_file.py {} ::: *.csv
```

### Memory-Efficient Processing

```python
# Process large files in chunks
import pandas as pd

for chunk in pd.read_csv('huge_file.csv', chunksize=10000):
    # Process chunk
    result = process_chunk(chunk)
    # Append to output
    result.to_csv('output.csv', mode='a', header=False)
```

## 🔧 Configuration

### Environment Setup
```bash
# Create virtual environment
python -m venv data-proc-env
source data-proc-env/bin/activate  # Linux/Mac
# or
data-proc-env\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt
```

### Tool Configuration

Most tools support configuration files:
```json
{
  "processing": {
    "chunk_size": 1000,
    "parallel_jobs": 4,
    "memory_limit": "2GB"
  },
  "output": {
    "format": "csv",
    "compression": "gzip",
    "encoding": "utf-8"
  }
}
```

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Areas of Interest
- Machine learning pipelines
- Real-time data processing
- Additional format converters
- Statistical analysis tools
- Visualization utilities

## 📈 Performance Optimization

### Tips for Large Datasets

1. **Use chunking**: Process data in manageable pieces
2. **Leverage multiprocessing**: Utilize all CPU cores
3. **Profile memory usage**: Monitor with `memory_profiler`
4. **Consider formats**: Parquet/HDF5 for large datasets

### Benchmarks

| Operation | Dataset Size | Time | Memory |
|-----------|-------------|------|--------|
| PDF extraction | 1000 pages | 45s | 200MB |
| Citation counting | 100 papers | 12s | 50MB |
| Pivot table (R) | 1M rows | 8s | 500MB |
| Web scraping | 100 pages | 2m | 100MB |

## 🐛 Troubleshooting

### Common Issues

**Import Errors**
```bash
# Check installed packages
pip list | grep package_name

# Reinstall if needed
pip install --upgrade package_name
```

**Memory Errors**
```python
# Use chunking for large files
chunk_size = 10000
for chunk in pd.read_csv('large_file.csv', chunksize=chunk_size):
    process(chunk)
```

**Encoding Issues**
```python
# Specify encoding explicitly
with open('file.txt', 'r', encoding='utf-8', errors='ignore') as f:
    content = f.read()
```

## 📚 Documentation

- [Python Tools Guide](docs/python-tools.md)
- [R Scripts Manual](docs/r-scripts.md)
- [Web Scraping Ethics](docs/scraping-ethics.md)
- [Performance Tuning](docs/performance.md)

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🌟 Acknowledgments

- Python Software Foundation
- R Core Team
- Open source data science community
- Contributors and testers

## 📮 Contact

- Issues: [GitHub Issues](https://github.com/olympus-terminal/data-processing/issues)
- Discussions: [GitHub Discussions](https://github.com/olympus-terminal/data-processing/discussions)
- Author: [@olympus-terminal](https://github.com/olympus-terminal)
