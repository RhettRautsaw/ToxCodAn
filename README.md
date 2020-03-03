![venomancer_logo](/venomancer_logo.png)

Venomancer
==========
<!---[![Latest GitHub release](https://img.shields.io/github/release/pedronachtigall/Venomancer.svg)](https://github.com/pedronachtigall/Venomancer/releases/latest) -->
<!---[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3403273.svg)](https://doi.org/10.5281/zenodo.3403273) -->
<!---[![Published in Genome Biology](https://img.shields.io/badge/published%20in-Genome%20Biology-blue.svg)](https://doi.org/10.1101/gr.214270.116) -->

**Venomancer** is a computational tool designed to detect and annotate toxin genes in transcriptome assembly.

Getting Started
=================

# Installation

Download the master folder and follow the steps below:

```
unzip Venomancer-master.zip
export PATH=$PATH:path/to/Venomancer-master/bin/
```
OR git clone the Venomancer respository and add the bin folder into your PATH:
```
git clone https://github.com/pedronachtigall/Venomancer.git
export PATH=$PATH:path/to/Venomancer/bin/
```

# Requirements

- [Python3](https://www.python.org/) and [Biopython](https://biopython.org/wiki/Download)
  - ```apt-get install python3-biopython```
- [Perl](https://www.perl.org/), [Bioperl](https://bioperl.org/) and [MCE](https://metacpan.org/release/MCE) (libmce-perl)
  - ```apt-get install bioperl libmce-perl```
- [CodAn](https://github.com/pedronachtigall/CodAn/)
- [NCBI-BLAST](https://www.ncbi.nlm.nih.gov/books/NBK279671/) (v2.9.0 or above)
- [SignalP-4.1](http://www.cbs.dtu.dk/cgi-bin/sw_request?signalp+4.1)

Ensure that all requirements are working properly.

# Usage

```
Usage: venomancer.py [options]

Options:
  -h, --help            show this help message and exit
  -s string, --sample=string
                        Optional - sample ID to be used in the output files
                        [default=venomancer]
  -t fasta, --transcripts=fasta
                        Mandatory - transcripts in FASTA format,
                        /path/to/transcripts.fasta
  -o folder, --output=folder
                        Optional - output folder, /path/to/output_folder; if
                        not defined, the output folder will be set in the
                        current directory [Venomancer_output]
  -m path, --model=path
                        Mandatory - path to model folder, /path/to/models
  -p boolean value, --signalp=boolean value
                        Optional - turn on/off the signalP filtering step, use
                        True to turn on or False to turn off [default=True]
  -c int, --cpu=int     Optional - number of threads to be used in each step
                        [default=1]
  -f int, --covprefilter=int
                        Optional - threshold value used as the minimum
                        coverage in the pre-filter step [default=90]
  -F int, --covtoxinfilter=int
                        Optional - threshold value used as the minimum
                        coverage in the toxin filter step [default=80]
```

Check our [tutorial](https://github.com/pedronachtigall/Venomancer/blob/master/TUTORIAL.md) to learn how to use Venomancer.

# Inputs
Venomancer need the transcripts in [fasta format](https://en.wikipedia.org/wiki/FASTA_format) as input.

# Outputs

Venomancer outputs the following files:
```
SampleID_Toxins_cds.fasta
SampleID_Toxins_pep.fasta
SampleID_Toxins_annotation.gtf
SampleID_Toxins_contigs.fasta
SampleID_PutativeToxins_cds.fasta
SampleID_PutativeToxins_contigs.fasta
SampleID_NonToxins_contigs.fasta

SampleID_Toxins_cds_SPfiltered.fasta (optional step)
SampleID_Toxins_pep_SPfiltered.fasta (optional step)
SampleID_Toxins_contigs_SPfiltered.fasta (optional step)
SampleID_Toxins_cds_SPfiltered_RedundancyFiltered.fasta (optional step)

signalp_annotation.gff (optional step)
RemoveRedundancy.log
```

Description of the output files:
```
cds -> coding sequence of the predicted toxins
pep -> protein sequence of the predicted toxins
contigs -> whole contigs containing the predicted CDSs
Toxins -> sequences with very high probability of being toxins
PutativeToxins -> sequences with medium/high probability of being toxins
NonToxins -> sequences with very low probability of being toxins
RedundancyFiltered -> CDSs with 100% identity filtered
SPfiltered -> signalP filtered sequences (optional step)
```
Reference
=========

If you use or discuss **Venomancer**, please cite:

Nachtigall et al., under review

License
=======

<!---[GNU GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) -->

Contact
=======
:bug::sos::speech_balloon:

To report bugs, to ask for help and to give any feedback, please contact **Pedro G. Nachtigall**: pedronachtigall@gmail.com

Frequently Asked Questions (FAQ)
================================
