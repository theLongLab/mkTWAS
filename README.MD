
## Users’ Manual of mkTWAS (Version 1.0.0)
### mkTWAS: Disentangling genetic feature selection and aggregation in transcriptome-wide association studies

<img src="https://github.com/theLongLab/FIGS/blob/master/1.png" width="800" height="600" alt="kTWAS"/><br/>

### Installation
mkTWAS is a batteries-included JAR executable. All needed external jar packages are included in the downloadable, mkTWAS.jar. To download all necessary files, users can use the command 
`git clone https://github.com/theLongLab/mkTWAS.git`
As we used an R package SKAT, the users have to install R and SKAT (https://cran.r-project.org/web/packages/SKAT/index.html.) The versions of R and R package SKAT that we have used on our platform are: version 2.0.0 for SKAT and version 3.5.1 for R. Other versions are not tested, although they may work. Users are also expected to have java (version: 1.8) on their platform. plink (v1.07, https://zzz.bwh.harvard.edu/plink/download.shtml) should also be installed.

Usage:

`java -jar mkTWAS.jar mkTWAS -format csv|plink -input_genotype INPUT_GENOTYPE_FILE -input_phenotype INPUT_PHENOTYPE_FILE -input_phenotype_column INPUT_PHENOTYPE_COLUMN_START:2 -input_phenotype_type PHENOTYPE_TYPE: continuous|binary 
-eqtl_info_path INPUT_EQTL_INFORMATION_FILE  -gene INPUT_ENSEMBL_GENE_ID  -plink PLINK_BINARY_FILE_PATH  -Rscript RSCRIPT_BINARY_FILE_PATH -output_folder OUTPUT_FOLDER_PATH`

Installation and a simple example are described below. Users can get the final p-value result under the folder: OUTPUT_FOLDER_PATH. 

You may try our example after "git clone". If trying csv format, the command line is:

`java -jar mkTWAS.jar mkTWAS -format csv -input_genotype EXAMPLE/CSV_FORMAT/example.csv -input_phenotype EXAMPLE/CSV_FORMAT/example.tsv -input_phenotype_column 2 -input_phenotype_type binary -eqtl_info_path DB/mkTWAS_WholeBlood.txt -gene ENSG00000250334.5 -plink /PATH/TO/plink -Rscript /PATH/TO/Rscript -output_folder /PATH/TO/OUT_FOLDER`

Otherwise, if users want to try plink format, the command line is:

`java -jar mkTWAS.jar mkTWAS -format plink -input_genotype EXAMPLE/PLINK_FORMAT/example.tped -input_phenotype EXAMPLE/PLINK_FORMAT/example.tfam -input_phenotype_column 6 -input_phenotype_type binary -eqtl_info_path DB/mkTWAS_WholeBlood.txt -gene ENSG00000250334.5 -plink /PATH/TO/plink -Rscript /PATH/TO/Rscript -output_folder /PATH/TO/OUT_FOLDER`

Please note that, to consistent with plink format, the phenotype is set to missing (normally represented by -9) if unspecified. It must be a numeric value. Case/control phenotypes are normally coded as control = 1, case = 2.The mkTWAS.result under /PATH/TO/OUT_FOLDER is the final output file by mkTWAS. 

### Contacts
Chen Cao, chen.cao@ucalgary.ca<br>
Quan Long, quan.long@ucalgary.ca<br>

### Copyright License (MIT Open Source)
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT
NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 
