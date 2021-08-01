# Genomic epidemiology of novel coronavirus - Asia-focused subsampling
# Getting ` nextstrain ` with conda
` conda create -n nextstrain -c conda-forge -c bioconda 
augur auspice nextstrain-cli nextalign snakemake awscli git pip ` \
 \
` conda activate nextstrain ` \
` nextstrain check-setup --set-default `
# Preparing data
` cd data ` \
` tar -xvf * ` \
` cd .. ` 
# Run 
` snakemake --profile my_profiles/example -p ` \
 (currently configured for 8 threads, you can specify `cores:`=2/4/8 (max: 8) in `my_profiles/example/config.yaml`)
# Visualize
` nextstrain view auspice` \
open: ` 127.0.0.1:4000 ` in browser and select dataset `ncov/asia/india`

![alt text](https://github.com/Ghanshyamchandra74/ncov_Asia/blob/main/scr.png?raw=true)


# Remote Visualize
` ssh -L 4000:localhost:4000 username@host ` \
` nextstrain view auspice` \
open: ` 127.0.0.1:4000 ` in remote browser \
 Reference : https://docs.nextstrain.org/en/latest/tutorials/SARS-CoV-2/index.html
