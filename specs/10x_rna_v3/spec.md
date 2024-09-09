# Example `seqspec` 10x Genomics v3

```yaml
!Assay
seqspec_version: 0.0.0
assay_id: 10xRNAv3
sequencer: Illumina
name: 10x-RNA-v3
doi: https://doi.org/10.1038/ncomms14049
date: null
description: 10xv3 single-cell RNA-seq
modalities:
  - rna
lib_struct: https://teichlab.github.io/scg_lib_structs/methods_html/10xChromium3.html
library_protocol: null
library_kit: null
sequence_protocol: null
sequence_kit: null
sequence_spec:
  - !Read
    read_id: R1.fastq.gz
    name: Read 1
    modality: illumina_truseq_prep
    primer_id: generic_primer1
    min_len: 1
    max_len: 250
    strand: pos
  - !Read
    read_id: R2.fastq.gz
    name: Read 2
    modality: illumina_truseq_prep
    primer_id: generic_primer2
    min_len: 1
    max_len: 250
    strand: neg
library_spec:
  - !Region
    region_id: rna
    region_type: rna
    name: rna
    sequence_type: joined
    sequence: AATGATACGGCGACCACCGAGATCTACACTCTTTCCCTACACGACGCTCTTCCGATCTNNNNNNNNNNNNNNNNNNNNNNNNNNNNXAGATCGGAAGAGCACACGTCTGAACTCCAGTCACNNNNNNNNATCTCGTATGCCGTCTTCTGCTTG
    min_len: 134
    max_len: 231
    onlist: null
    regions:
      - !Region
        region_id: illumina_p5
        region_type: illumina_p5
        name: Illumina P5
        sequence_type: fixed
        sequence: AATGATACGGCGACCACCGAGATCTACAC
        min_len: 29
        max_len: 29
        onlist: null
        regions: null
        parent_id: rna
      - !Region
        region_id: truseq_read1
        region_type: truseq_read1
        name: Truseq Read 1
        sequence_type: fixed
        sequence: TCTTTCCCTACACGACGCTCTTCCGATCT
        min_len: 10
        max_len: 10
        onlist: null
        regions: null
        parent_id: rna
      - !Region
        region_id: R1.fastq.gz
        region_type: fastq
        name: Read 1 FASTQ
        sequence_type: joined
        sequence: NNNNNNNNNNNNNNNNNNNNNNNNNNNN
        min_len: 28
        max_len: 28
        onlist: null
        regions:
          - !Region
            region_id: barcode
            region_type: barcode
            name: Cell Barcode
            sequence_type: onlist
            sequence: NNNNNNNNNNNNNNNN
            min_len: 16
            max_len: 16
            onlist: !Onlist
              filename: 3M-february-2018.txt.gz
              md5: null
              location: local
            regions: null
            parent_id: R1.fastq.gz
          - !Region
            region_id: umi
            region_type: umi
            name: UMI
            sequence_type: random
            sequence: NNNNNNNNNNNN
            min_len: 12
            max_len: 12
            onlist: null
            regions: null
            parent_id: R1.fastq.gz
        parent_id: rna
      - !Region
        region_id: R2.fastq.gz
        region_type: fastq
        name: Read 2 FASTQ
        sequence_type: joined
        sequence: X
        min_len: 1
        max_len: 98
        onlist: null
        regions:
          - !Region
            region_id: cdna
            region_type: cdna
            name: cdna
            sequence_type: random
            sequence: X
            min_len: 1
            max_len: 98
            onlist: null
            regions: null
            parent_id: R2.fastq.gz
        parent_id: rna
      - !Region
        prder: 4
        region_id: truseq_read2
        region_type: truseq_read2
        name: Truseq Read 2
        sequence_type: fixed
        sequence: AGATCGGAAGAGCACACGTCTGAACTCCAGTCAC
        min_len: 34
        max_len: 34
        onlist: null
        regions: null
        parent_id: rna
      - !Region
        region_id: I1.fastq.gz
        region_type: fastq
        name: Index Read 2
        sequence_type: joined
        sequence: NNNNNNNN
        min_len: 8
        max_len: 8
        onlist: null
        regions:
          - !Region
            region_id: index7
            region_type: index7
            name: Truseq Read 2
            sequence_type: onlist
            sequence: NNNNNNNN
            min_len: 8
            max_len: 8
            onlist: !Onlist
              filename: index7_onlist.txt
              md5: null
              location: local
            regions: null
            parent_id: I1.fastq.gz
        parent_id: rna
      - !Region
        region_id: illumina_p7
        region_type: illumina_p7
        name: Illumina P7
        sequence_type: fixed
        sequence: ATCTCGTATGCCGTCTTCTGCTTG
        min_len: 24
        max_len: 24
        onlist: null
        regions: null
        parent_id: rna
    parent_id: null
```
