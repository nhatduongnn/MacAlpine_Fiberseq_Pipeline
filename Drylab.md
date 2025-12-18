# Sequencing
- Sequencing was done on MinION with flowcell R10.4.1
- Made to to tell sequencing machine to output POD5 files.

---
<br>
<br>
<br>
<br>
<br>


# Data Processing

## Raw Signal to Aligned Reads
### Programs:

Dorado (version 0.9.1)

### Workflow

- Use Dorado basecaller to convert POD5 to non-aligned BAM file (sup model and 6mA methylation)
- Use Dorado aligner to align to reference genome
- Use Dorado demux to demultiplex the data and get barcode information

**At this point we should have aligned BAM files**

---

## Aligned Reads to Methylation Files

### Programs:
Modkit
All data processing in this step was done on a cluster with one NVIDIA A5000 gpu 

### Workflow

- Use modkit extract to obtain a (very big) file with each row being one methylation on a single fiber. 
- Use modkit pileup to obtain a file with each row being summary for each methylated position in the genome

---
## Plotting and making fiber figures

### Programs:

Python 3

### Workflow:

Load in a section of modkit extract result file. This file should have info like the start and end of fibers and location of methylation. This should be enough to recreate fiber plots. 
These files can be really big so efficiently loading in the file and storing the file is potentially necessary








