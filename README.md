## Workflow for how to generate a phylogeny with divergence times from nucleotide alignments using BEAST.
### Once you "tame the beast" with this workflow, there are tons of options you should add and update specific to your project. 

1) install BEAST v 2.6.1
  -NOTE: in my experience, the mac version did not update to 2.6.1, so I decided to use the windows version
2) Perform multiple sequence alignment using MUSCLE and export as NEXUS format.
3) launch beauti from the beast directory and import alignment (nexus file)
  -Change the site model from JC69 to GTR.
  -Change CLock model to RELAXED LOG NORMAL.
  -Add priors: scroll up to normal distribution and select monophyletic.
  -Include a prior with all samples except your outgroup and select monophyletic.
  -change MCMC chain length to 800000.
  - save.
 4) launch beast, and input the .xml file from beati and then run it.
 5) Launch TreeAnnotator 2.6 (separate install) and input your trees file. 
  - select MAXIMUM SUM OF CLADE CREDIBILITIES. (Best overall tree)
  - select new output file.
 6) visulize best tree from TreeAnnotator with Figtree (separate install)
  - Under Time scale, click scale to root (260MYA for Drosophila in my case)
  - Click node labels - median height.
  - Scale axis, REVERSE AXIS
  - Under node labels - select height 95% HPD to see confidence interval (I add these into the PDF later).
