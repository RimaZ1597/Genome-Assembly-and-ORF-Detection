# Greedy Genome Assembly and ORF Detection Pipeline

This repository contains Python scripts that implement a small-scale genome assembly workflow using a **greedy overlap algorithm**, followed by **coverage analysis** and **ORF detection using motif-based scoring**. The project demonstrates how raw sequencing reads can be assembled into contigs and how biological features such as ORFs can be extracted from assembled sequences.

---

### **1. Greedy Read Assembly**
The assembly script:
- Reads short DNA reads from a text file  
- Computes pairwise overlaps using suffix–prefix matching  
- Merges reads into longer contigs based on a minimum overlap `k`  
- Removes redundant contigs  
- Writes final contigs to FASTA (`RimaAssignment1.fasta`) and CSV  

**Output:**  
- `merged_all_contigs.csv`  
- `RimaAssignment1.fasta`

---

### **2. Contig Overlap Detection & Merging**
Includes:
- Finding contigs that fully or partially contain each other  
- Merging nested or overlapping contigs  
- Producing a minimal set of long, non-redundant contigs  

---

### **3. Coverage Analysis**
- Calculates how many reads map to each contig  
- Generates a horizontal bar plot of read coverage

---

### **4. ORF Detection Using Motif Scoring**
The ORF detection script:
- Reads contigs from a FASTA file  
- Uses a **13-base motif scoring matrix**  
- Searches for high-scoring start sites (ATG/GTG)  
- Extends ORFs to stop codons (TAA, TAG, TGA)  
- Ensures ORF ≥ minimum length  
- Writes annotated ORFs to a FASTA output (`rima.fa`)

---
## Purpose of This Project

* How genome assembly works using a greedy overlap approach
* How contigs can be refined and merged
* How can biological features, such as ORFs, be extracted using motifs and codon logic?
