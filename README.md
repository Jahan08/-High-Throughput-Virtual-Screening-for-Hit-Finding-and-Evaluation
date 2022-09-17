# The Learning Objectives for the course are summarized below:

* Understand the relevance of virtual screening and identify the benefits of screening very large ligand libraries
* Recall and apply the virtual screening concepts, including docking, active learning, and shape screening
* Recall and apply knowledge of target validation by preparing a target for structure-based virtual screening 
* Recall and apply knowledge of library selection by preparing and filtering a ligand library for screening
* Understand and demonstrate the importance of setting up, running and analyzing validation studies and then running perspective screens using active learning, docking, and shape screening tools
* Understand and demonstrate methods of post-screening analysis, including; filtering, clustering, diversity enhancement, and comparison of scoring functions
* Recall examples of methods that can be used after high-throughput virtual screening 
* Complete a case study covering the HTVS process; assess various aspects of the screen, justify hit selection and submit absolute binding free energy perturbation predictions for chosen hits

As well as using Maestro in this course, participants will learn how to submit jobs and run Schrödinger scripts via the command line. For a useful overview, see our Using the Command Line with the Schrödinger Platform guidance.

# Module 1: Some terms to understand

•	Absorption: The movement of a compound/drug from the site of administration to the bloodstream. This process involves several phases and depends upon the method of delivery (oral, topical, intravenous etc.). Lipinski's rule of 5 famously predicts that poor absorption is more likely when there are more than 5 hydrogen bond donors, 10 hydrogen bond acceptors, a molecular weight greater than 500 and a calculated LogP greater than 5.

•	Chemical stability: The stability of a drug is critical to efficacy, as the loss of a drug through a chemical reaction will result in reduction of potency and may result in degradation into a toxic substance. To learn more about chemical stability of drug substances, read this chapter from the Stability of Drugs and Dosage Forms.

•	Directed screen: A type of high-throughput screen that tests large compound libraries with user-intervention involved in the selecting of compound chemotypes.

•	DNA encoded libraries (DEL): A technology for the synthesis and screening of large collections of small molecule compounds by the conjugation of chemical compounds or building blocks to short DNA fragments that serve as identification bar codes through PCR amplification. To learn more, read through the DEL Wikipedia page that is very well written

•	Drug discovery pipeline: The process by which hits are identified, optimized to leads, and leads are tested for suitability as new chemical entities (NCEs). The NCEs are validated before approval by the FDA.

•	Fragment Based Drug Discovery: A series of methods in drug discovery that use small organic molecules which are small in size and low in molecular weight and may bind only weakly to the biological target (protein), and then grow them or combine them to produce a lead compound with a higher affinity. To learn more, read this introduction to fragment-based drug discovery by Carmot Therapeutics.

•	Free energy perturbation (FEP): An alchemical approach that uses molecular dynamics simulations or Monte Carlo methods to compute the free energy differences between two ligands in solution and in a protein binding site. To learn about the industry standard FEP+ technology read the Schrödinger webpage. To learn more about how this method has been successful in predicting GPCR binding affinities, see this high-level video or read the corresponding Open Access article.

•	Hit: A small molecule that is known to inhibit or bind to a target in drug discovery. Most times, this hit molecule does not have optimized properties or high enough affinity to fully satisfy the needs of a project. Functional groups on the hit are usually altered to address this in what will become a lead molecule. 

•	Lead ( or Core) Hopping: the identification of molecular structures that have the same functional inhibition of a given target with significantly different molecular backbones or core moieties.

•	Ligand-based virtual screening: Using the structure and chemical properties of a hit ligand or series of ligands to assess compounds as potential binders on the computer.

•	Metabolic stability: The stability of a drug within a cellular environment, as many metabolic enzymes within our cells (p450s, oxidases, aldo-ketoreductases, esterases, conjugases etc), are able to degrade drugs into other compounds thus reducing potency and potentially creating toxic substances. To read more on metabolic stability in drug discovery, read this article from Millenium: The Takeda Oncology company.

•	Random screen: A type of high-throughput screen that tests large compound libraries without user-intervention involved in selecting compound chemotypes.

•	Safety: Drug safety is important to assess, including side effects due to off-target effects, as well as toxicity issues that arise from chemical and metabolic instability. To read more on common methods for assessing drug safety, see this Nature correspondence.

•	Solubility in drug discovery: A measure of how well a small molecule dissolves in the blood, usually predicted through the solubility coefficient of a compound in water versus octanol. For more background on the relationship between solubility and physicochemical properties, see this American Pharmaceutical Review article.

•	Structure-activity relationship (SAR): A relationship that is built based on analyzing multiple compounds with similar cores but different functional groups to understand the impact that chemical structure changes have on the activity of the compound against a target.

•	Structure-based drug design (SBDD): Using the information present in a macromolecule or protein structure to identify hits and optimize drug-like properties.

•	Structure-based virtual screening: Using the structure and chemical properties of a binding site on a macromolecule or protein target to assess compounds as potential binders on the computer.

•	Target: A macromolecule (most commonly a protein) that will be targeted by a small molecule in a drug discovery project. Often the small molecule will cause some conformational change or lock the macromolecule into a particular conformation and thus affect that macromolecule's activity and downstream signaling pathways.


# Module 1.3 The Benefits of Screening Ultra-Large Libraries Transcript (Schoichet paper: https://www.nature.com/articles/s41586-019-0917-9)

* Expanding Chemical Space : Getting new medicines to patients faster is the ultimate goal for drug discovery teams. Yet chemical space is vast, and only a tiny fraction of the billions of potentially pharmacologically active molecules are available to screen physically. Structure-based docking can screen virtual libraries of great size and diversity, enabling us to select only the best-fitting molecules for synthesis and testing.
While physical compound collections typically include less than 20 million compounds......Recent advances, for example the advent of DNA encoded libraries, have extended the scale of screening libraries to the trillions. 

  * The GDB-17 (https://gdb.unibe.ch/downloads/) (GDB-11 enumerates small organic molecules up to 11 atoms of C, N, O and F following simple chemical stability and synthetic feasibility rules. GDB-13 enumerates small organic molecules up to 13 atoms of C, N, O, S and Cl following simple chemical stability and synthetic feasibility rules. With 977 468 314 structures, GDB-13 is the largest publicly available small organic molecule database to date.) 

  GDB-17, is the so-called “chemical universe database” , covers all molecules with up to 17 atoms that contain C, N, O, S, and halogen atoms. This database contains over 166 billion compounds. Virtual screening methods are not yet regularly being used at quite that scale, but they are starting to be used with databases containing more than 1 billion compounds, and there are multiple vendors who have amassed synthetically tractable libraries with greater than 100 million compounds.

  * Enamine REAL database : The REAL Database is one of the ways to explore the REAL Compounds. It is a classical database of enumerated structures. The database is a tool to find new hit molecules using large-scale virtual screening and to search for analogs of your hit molecules. The REAL Database is accessible as SMILES, SDF, and it is searchable on Enaminestore.
The current release of the REAL database comprises over 5.5 billion molecules which comply with “rule of 5“ and Veber criteria: MW≤500, SlogP≤5, HBA≤10, HBD≤5, rotatable bonds≤10, and TPSA≤140. (https://enamine.net/compound-collections/real-compounds/real-database)

The paper focuses on the Enamine REAL database, a collection with a vast number of dockabe compounds which can, in theory, be synthesized based on 130 reactions and 70 000 building blocks (with reported synthesis success rates of around 85% or higher). In late 2020, the Enamine REAL database comprised 1.36 billion compounds and it continues to grow.
  
   * Another important feature of the Enamine REAL database goes beyond just library size, and is a key factor in library curation. We are of course talking about the diversity of the screening library. Compound diversity is key as it allows you to potentially identify several diverse hits, and perhaps follow up on them all in parallel.
   
   The Shoichet paper authors identified the total number of unique scaffolds in the Enamine database, and then counted how many molecules they could find in the library that had that scaffold. As you can see from the plot on this slide, there is a strong left skew to the distribution, with it being more likely that there are few compounds with a given scaffold than many. An additional analysis showed that for roughly every 20 new compounds, you’ll stumble across a new scaffold. While this may not sound like much, it does serve as a compelling justification for the value of screening larger libraries - the larger the library, the more unique scaffolds you will be evaluating, and, in turn, the more total shots on goal you will have for finding useful hits.
   
   ## Some issues or concern regarding screening large database
   
   * Firstly, docking cannot accurately predict binding affinity and can result in many false positive hits
   * There was also the concern that large compound libraries might overwhelm the active compounds with inactive or “decoy” compounds
       -> A preliminary study was set up with this in mind, and set out to test how hit rates would vary as the library increased from tens of thousands to hundreds of millions of compounds. For a series of targets, known binders were docked along with property-matched decoys, and the authors looked at how the actives ranked as the decoy to active ratio increased. They expected the noise to overwhelm the signal, but this was not the case.
       -> As the authors noted, the targets for which docking performed well with a high ligand to decoy ratio, perform better as the library size is increased. On the other hand, targets such as PUR2 where the docking performance with a higher ligand to decoy ratio was only ok with a lower library size, performed considerably worse as the library was increased. This suggests that models that work well would be expected to work even better as the library size increases, and not, as the authors feared “that inaccurate docking scores and a vast chemical space...conspire to overwhelm the true actives with docking decoys.”
   
 * Screening Process : Authors docked the Enamine database, which at the time contained 99 million molecules, against AmpC, a beta lactamase enzyme. Starting with 99 million compounds, clustering the top 1 million (by staffold and topological similarity). Then, in order to identify only novel compounds, compounds which were similar to known AmpC inhibitors or that were similar to molecules that already existed in the in-stock compound library were excluded. 51 of the highest ranking compounds were selected for testing, of which 85% were successfully synthesized. Five of these 44 molecules showed inhibitory activity against the target, with Ki values ranging from 1.3 to 400 micromolar. 90 more high scoring analogues were chosen and synthesized. More than half of these were active and most so than the original hits. The authors note that the “the ability to optimize affinity by finding analogs within the library attests to its depth of coverage for many chemotypes. Finally, several of the high affinity compounds were co-crystallized with AmpC and encouragingly, the binding poses showed good agreement with docking pose predictions.
 
    The authors were even more ambitious with the second target, the D4 Dopamine Receptor - docking 138 million compounds. Like for the previous target, any compounds that were found to be similar to known binders in existing libraries were filtered out, as novelty was the goal. A whopping 589 compounds were selected - roughly two-thirds by docking score alone, and the rest were chosen manually from the 1000 best ranked clusters. A total of 81 compounds were found to have Ki values ranging from 18.4 nM to 8.3 μM. Interestingly, several of the ligands engaged with a part of the receptor that is unique for the D4 receptor and not found in the D2 or D3 subtypes - something that was not frequently seen with previously known actives, and which likely is responsible for the strong selectivity for several of the compounds.
        
    ## Some issues regarding pre-clustering
    
    The obvious question after looking through both of these cases is - great, you recovered a lot of diversity, but what if you pre-clustered the library and only selected a single representative structure from each cluster for docking? Presumably, this would help find diverse structures, and if there was a hit with any representative structure more of the cluster could then be analyzed. The authors preempted this question by doing just that and looked at how pre-clustering affected where the actives ranked. A set of 47 actives fell down the list by an average of over 1 million places, suggesting that pre-clustering a library will likely result in hits being missed. The authors would have likely identified other hits from this screen, but these 47 confirmed hits would not have been identified because the representative structures from their clusters did not dock as well. Clustering after docking can be helpful for manual selection of compounds from the top ranked compounds, but pre-clustering as a means to screening fewer compounds, although time-saving, doesn’t quite work as well as one might like.
    
    ## how does docking rank predict binding likelihood
    
    To do this, the authors developed what they called “hit-rate curves” that are a function of the docking score. They also established docking score ranges from which they would experimentally validate the hit rate. The 549 compounds that were chosen for synthesis were actually chosen such that they would cover 12 different ranges or tranches, as shown in the plot. While the analysis showed, as expected, high false-negative and false-positive rates, it also showed that for at least the D4 system, the binding was predicted quite well by docking score.
A more general take away from this analysis is that hit rate can be expected to increase in regions of higher docking scores. This does level off near the very top, suggesting that it might make sense to impose a scoring function cutoff on the list of compounds to synthesize or purchase, but in the very top of the list, docking is not so good at differentiating between the high affinity compounds.

# 2.2 Active Learning

Active Learning technology offers a solution to this problem. Schrodingers Active Learning workflows train a machine learning (ML) model on physics-based data, such as Glide docking scores, iteratively sampled from a full library using our deep-learning powered QSAR platform, DeepChem/AutoQSAR.

Machine learning algorithms build a model based on sample data, known as "training data", in order to make predictions or decisions without being explicitly programmed to do so.
The 2D chemical structure of each molecule in a screening library is converted into a vector of numbers, in order for it to be included in the neural network. By docking only a fraction of the full library and using the scores to train a machine learning model, the entire library can be evaluated at a fraction of the speed. The top-ranked compounds predicted by the ML model can then undergo conventional virtual screening docking approaches.

Say we want to dock a library of 10 Billion compounds - this is our complete dataset, and we only need a 2-dimensional representation of each compound in SMILES format to start this process.

Depending on our complete library size, we then decide how many compounds we want to use to train the Machine learning model. The minimum here is 15 compounds, but the default is 100,000 compounds.

The next step is to dock the selected subset of our library, so in our example let’s say we have chosen to dock 100,000 compounds from our 10 billion compound library.

Docking scores are analyzed together with the compound vector information

And the data from the docked ligands are used to train and generate a ML model, which can then be used to rank all of the compounds in the entire 10 billion compound library. Evaluating the entire population takes around 1milisecond per ligand. This is much faster than docking with Glide, which can take around 30 seconds per ligand.

# Module 3 Target Validation for structure-based virtual screening

In order to discern whether our target of interest can be used in a virtual screening campaign, we need to answer a series of questions, ranging from “is there an available structure of our target” through to “where are the druggable regions and/or potency handles within the binding site”. We can use a series of computational tools to help answer these questions and inform the preparation of our target prior to a virtual screen.

The first thing we want to do is get an idea of the quality of our protein target. It’s a good idea to carefully read through the publication that goes alongside the PDB entry, as well as the entry itself, to get an idea of whether the protein was engineered or stabilized to aid expression or
crystallization. After we have an idea of the target we might like to use for a virtual screen, we can get some more information about its quality by generating a Protein Reliability Report.

  
## Module 3.1 Target Inspection and Preparation

 * Reviewing and Choosing a structure
 
 * Protein Reliability Report metrices - to get an idea of the quality of the structure
 
 * Preparing the structures with the protein preparation wizard - repair the missing H, missing side chains, missing loops, alternate positions for the side chains and more
    
    Preprocess (keep water molecules since we are going to use watermap, check literature to check pH) -> Review and MOdify -> Optimize and Minimize 
 
 * Primex - PrimeX can be used to review the density and help make judgments about side-chain orientation, particularly where alternate positions are presented (we can use this during the  protein preparation since primex can tell about the electron density of the side chains and their alternate positions if any, we will take that alternate position which shows the higher density.)
 
 Looking at the electron density can often provide insight when selecting alternate positions, but can be inconclusive as you found. In this case, if the side chain is in the binding pocket it would be good practice to create multiple copies of the structure and to commit a different alternate position for each so that all the options are represented. You could then run your virtual screen with multiple versions of the same protein since as you mentioned, subtle differences may affect ligand binding.
 
 Similarly, depending on the net charge and the location of protons, some residues such as histidine (HIS) can adopt multiple states. With histidine we see HIP (+1 charged, both δ- and ε-nitrogens protonated), HID (neutral, δ-nitrogen protonated), and HIE (neutral, ε-nitrogen protonated). In Meastro, any state changes or flips that have occurred during the preparation process will be labeled (e.g. HIE, HID, FLIP). I wanted to highlight that there are usually some HIS to HIE tautomerizations as well as an ASN flip near the binding pocket, and if this is the case, it would be worth inspecting these changes (to confirm they make sense) and it may potentially be worth taking forward multiple versions of this structure with the various tautomers/flips represented since these differences can influence future ligand docking and scoring.
 
 Histidine is an essential amino acid whose side-chain pKa (~6) is closest, among all amino acids, to the physiological pH. Thus, small changes in the environmental pH can readily change the histidine charged state. At low pH, both imidazole nitrogens are protonated to give the cationic imidazolium. Near pH 7, two neutral tautomers exist: the Nε2-protonated τ tautomer and the Nδ1-protonated π tautomer. At mildly basic pH, the backbone Nα becomes deprotonated to give an anionic histidine, whose side chain is neutral in either tautomeric state. At even higher pH or when complexed with metal ions, the imidazole can lose another proton to give an imidazolate ion.1,2 Neutral histidine can serve as a general base and a common coordinating ligand for transition metals, while cationic histidine can serve as a general acid and hydrogen-bond (H-bond) donor. Because of its rich chemistry and pH sensitivity in the physiologically relevant range, histidine is found in the active sites of many proteins and plays key roles in enzyme catalysis,3,4 proton conduction,5,6 proton pumps,7 photosynthetic complexes,8 and metalloproteins.9,10 In addition to protonation chemistry and metal coordination, the neutral imidazole of histidine can combine tautomerization with ring flips (180° χ2 angle changes) to interconvert the protonated and unprotonated nitrogens without significantly changing the space occupied by the ring. Thus, histidine side-chain rotamerization is often important for protein function.
 
 * Protein reliability report to see how structure change during preparation
 
 ### Note - sometimes protein reliability report results appear to be worse after protein preparation. Inspect the elements that are “worse” and decide if these are of genuine concern or not. E.g. if steric clashes have increased, assess whether these clashes are from crystal mates (toggle on Show crystal mates in the Protein Reliability Report panel). Neighboring crystals of the same protein are often not biologically relevant.
 
 * SiteMap - Explore the druggability of the binding site. SiteMap will identify pockets either with or without using a known ligand. The visual representation is split into hydrophobic yellow regions, and red hydrogen bond acceptor and blue hydrogen bond donor regions and metal binding regions colored pink. A number of scores are also generated, and these can be used to assess whether the target’s binding pocket is worth exploring further. The Balance metric is a measure of whether a site has a good mixture of hydrophobic and polar regions for ligands to bind to, and the Volume of the pocket or binding site is a useful measure that allows us to identify if it will be able to accommodate ligands of a certain size.

### Note : Before analyzing the prepared protein structure we are going to remove all the water molecules. Sitemap generate hydrophobic and hydrophylic contour map. When analyzing SiteMap results, it is recommended to look for a SiteScore and DScore > 1, a balance > 0.3 and a volume > 225

### For more - https://www.schrodinger.com/sites/default/files/s3/mkt/Documentation/2021-1/docs/Documentation.htm#sitemap_user_manual/sitemap_intro_overview.htm

### For more https://www.schrodinger.com/sites/default/files/s3/mkt/Documentation/2021-1/docs/Documentation.htm#sitemap_user_manual/sitemap_methodology_evaluate_sites.htm%3FTocPath%3DUser%2520Manuals%7CSiteMap%2520User%2520Manual%7CHow%2520SiteMap%2520Works%7C_____3
 
 * Mixed-Solvent MD - This protocol simulates the target of interest (GPCR, kinase, ion channel, etc.) in a solution of water and a co-solvent, like benzene or any other fragment-like molecule. During the simulation, the co-solvent molecules interact with the surface of the protein, revealing binding hotspots. These hotspots have been proven to correlate very well with actual pockets. Furthermore, binding modes for the probes can be extracted, which can prove very valuable, as the binding mode of bigger, drug-like molecules could mirror that of the probe.
We can run multiple different fragments in parallel to conduct a virtual screening campaign.

### Note - Mixed-solvent MD is recommended where SiteMap Fails to generate desired score and this protocol can provide more details (sometimes SiteMap can outperform this protocol) about the potential and existing binding sites than SiteMap. But this process is more expensive than SiteMap.

### find the binding site using PyMol : https://www.youtube.com/watch?v=49q1w0EuuhU

 * WaterMap - Often crystal structures contain water molecules, and as well as inspecting these carefully to identify if any particular water molecules involved in ligand binding for our target, WaterMap can help identify water molecules that could be expelled from a pocket on ligand binding.

WaterMap is different from sitemap and MxMD in that it is used to determine hydration-site thermodynamics. 

### Note - The preparation of a system is extremely important prior to performing a WaterMap calculation and can have a profound influence on the quality of results that emerge from it. Any unusual residue charges or incorrectly flipped residues can drastically alter the hydration structure seen in the final WaterMap

It is a best practice to always run WaterMap on both the apo- and holo-structures. If there are any apo hydration sites that have the same or higher ΔG in the holo map, those sites should be considered as targets for displacement. Additionally, drug design efforts should focus on displacing hydration sites that have high TΔS (entropy), but low ΔH (enthalpy).

Apo WaterMap job: Protein without the Ligand. WaterMap uses the location of the ligand to identify the binding site and calculates the thermodynamics for the water molecules in this region

Holo WaterMap Job: Protein with Ligand

### Result analysis - red spheres imply very high energy hydration sites, meaning they are highly unstable and if the apo WaterMap shows a cluster of high-energy hydration sites in the binding site region that are highly unstable and in the holo WaterMap almost all those high-energy waters have been displaced by the ligand. This implies that a drug-sized molecule (that can be accommodated in this binding site), will receive significant binding affinity from simply occupying the binding site, thus confirming the target’s druggability.

## Module 3 Assignment : In the Module 3 Assignment Instructions workflow, you carried out target preparation and validation tasks for 2OWB and 2RKU. For details see the attached file where I applied (RSCB.org, Protein Preparation wizard, Protein Reliability Report, Primex, SiteMap, WaterMap)

### Note - Protein can contain multiple chains, so WaterMap and SiteMap analysis must be conducted on multiple chains separately 

# Module 4.1

In the Module 3 assignment, we prepared and validated two PLK1 structures (2OWB and 2RKU). In this module, we are going to prepare ligand libraries, some of which contain compounds that are known PLK1 binders.

Let’s start by profiling and filtering the PLK1 DUD-E library. This library contains a mixture of known actives and decoys and will be used as part of our validation study to assess whether our targets can identify known binders effectively. 

### Note - to know more background information (see uploaded file Module_4_Background_Required_Reading.pdf)

## Module 4.1a DUD-E (decoys) Library Profiling and Filtering

We have prepared DUD-E ligand library for PLK1 kinase, which is a csv file with SMILE string, CHEMBL ID, Biological Activity Data. Next step is to profile the ligand library by analysing the properties i.e. HBA, HBD, MW, AlogP, PSA from the SMILES string and CHEMBL ID. By plotting the ligands (Druglike, leadlike, Near-drug like, Fragment, non-druglike) we can know a little more about the properties of the ligands in our library. let’s filter the library to remove the Non-Druglike and fragment compounds. We now have a filtered .csv file (PLK1_DUDE_screen_filtered.csv) containing 5782 compounds that we will prepare using LigPrep

## Module 4.1b Decoys Ligand library preparation
We used Maestro (LigPrep) to prepare filtered file.

## Module 4.1c Cognate or co-crystallized Ligand preparation
We used Maestro (LigPrep) to prepare cognate ligands.

## Module 4.1d Enamine REAL Ligand library filtering and preparation
In this section, for ligand-based virtual screening, we profiled and filtered ~2 million compound subset of the Enamine REAL library. This subset of just over 2 million compounds was created by Schrödinger scientists for use in this course. The full Enamine REAL library comprises over 1.95 billion compounds, so in the interest of time and compute resources, we screened a random subset of the full library.

Enamine REAL ~2M compounds library contains SMILES String and compund ID (ZINC ID) then profiling and filetring were condusted as like as for the DUD-E library. After filtering we got 1875200 compounds.

### Note Ligand should be prepared at the same pH as the proteins were prepared. 

# Module 4.2 Receptor Grid generation

* Step 1 Identifying interacting waters : kept the water molecules which interact with ligands and also facilitate the interaction between ligand and protein residue/s

* Step 2 Grid Generation : We have created 3 recpetor grids for 2OWB (4 waters, 1 water and dry) and another 3 receptor grids for 2RKU (3 waters, 1 water and dry). The grids have optional positional and hydrogen bonding constraints that we can choose to use in docking studies. It is good practice to create a number of grids for prepared structure, particularly if there is water in the binding pocket, in order to assess whether this helps or hinders docking.


# Module 4.3
For shape-based screening of a chemical library with GPU shape, we prepared the library and probe molecules. We select 10 probe(template to compare with) molecules from cognate ligands as well as the PLK1 DUD-E actives(118) we prepared earlier. We can use just one probe, but increasing the number and diversity probes generally improves performance, though this begins to saturate at around 10 molecules. We used the tools within Maestro to cluster these active PLK1 compounds and select 10 diverse probes to use in our Shape screen. 

* Selecting Template (probe) molecules for the screen

The first step in executing a Shape screen of a chemical library is to construct a shape-based model of known small-molecule binders. Each molecule in the screening deck will be analyzed in the same way and compared with the profiles of each of the template or probe molecules. The ability of Shape to recover true actives is influenced by the diversity and number of probes. We can use just one probe, but increasing the number and diversity probes generally improves performance, though this begins to saturate at around 10 molecules. We will use the two PLK1 (2OWB and 2RKU) cognate ligands that we prepared using LigPrep previously, and we additionally used the known 118 actives from the filtered and LigPrepped PLK1 DUD-E library. We used the tools within Maestro to cluster these active PLK1 compounds and select 10 diverse probes to use in our Shape screen.

 * Ligand alignment
 
 * Conduct Ligand-based Virtual Screening to create probe or template molecules
 
 Fingerprint Similarity -> Fingerprint -> (Radial, For Atom Typing Scheme, choose 4. Atoms distinguished by functional type: {H}, {C}, {F,Cl}, {Br,I}, {N,O}, {S}, {other}; bonds by hybridization) -> Similarity (Tanimoto) -> cluster (10 clusters based on fingerprint similarity)
 
 Fingerprint : Molecular fingerprints are a way of encoding the structure of a molecule. The most common type of fingerprint is a series of binary digits (bits) that represent the presence or absence of particular substructures in the molecule. Comparing fingerprints allows you to determine the similarity between two molecules, to find matches to a query substructure, etc.
 
 Tanimoto : Two fingerprints are most commonly compared with the Tanimoto similarity metric (taking a value between 0 and 1, with 1 corresponding to identical fingerprints
 
 * Preparing a screening deck for shape
 
 We screened a subset of the enamine REAL library containing ~2M compounds. We already have filtered Enamine REAL library (convert .csv to .sim filetype). To screen them we conducted Shape Screening (Ligand-based virtual screening). we used Typed Pharmacophore is the recommended shape type and requires that a shape from a probe molecule will only match a ligand from the screening deck when the two spheres have matching pharmacophore types.
 
 ### for more : https://www.schrodinger.com//sites/default/files/s3/mkt/Documentation/2021-1/docs/Documentation.htm#maestro_tools_help/canvas_cluster.html?

# Module 5.1a Docking Validation with Cognate Ligands

The first part of our docking validation study is to assess how well Glide can reproduce the known cognate ligand binding poses.

# Module 5.1b Docking validation with DUD-E Library

In this tutorial, we built on the methods used in the previous tutorial and use Glide to to dock the filtered PLK1 DUD-E ligand library, both with and without grid-based constraints, for each of the 2OWB and 2RKU receptor grids. Docking validation studies such as this were used to further assess if our structures and docking methodology can demonstrate enrichment of known active compounds over decoys.

* Step 1 DUD-E Filtered Ligand Docking with and without Constraints (Receptor based virtual screening -> Ligand Docking )
* Step 2 Calculation Enrichment : The first step in enrichment calculation is creating a file containing only the known actives. Our filtered DUD-E library contained a total of 5782 compounds, 118 of which were known actives. We will use the PLK1_DUDE_screen_filtered.csv file that we created in Module 4 to create a file containing only active compounds.

This step can show the efficiency of the receptor grids during docking to screen the actives compounds from the mixture of actives and decoys

# Module 5.1 Assignment (uploaded)

# Module 5.2 Evaluating a Large Ligand Library with Active Learning Glide

Here we used Active Learning Glide (pre-run) in “evaluate” mode with our filtered Enamine REAL subset library (~2 million compounds). Evaluate mode allows us to use a pre -generated ML model to rank a large library to compounds, then choose the number (in this case we will use 5%, which will be prepared with LigPrep) of top-scoring compounds to dock to our validated 2OWB_dry_grid using Glide SP. 

The ML model has been generated already, so we will be using Active Learning Glide in “evaluate” mode. This mode uses the pre-generated model to rank the entire library and then run Glide SP docking for a specified percentage of the top ranked compounds. 

# Module 5.3 Ligand Based Virtual Screening with GPU shape

we have run a GPU Shape screen. In Module 4.3, the 2OWB and 2RKU cognate ligands, as well as the active ligands from the filtered PLK1 DUD-E library, were clustered to create a representative yet diverse set of 10 probes. These were used to screen to large ligand library, our enamine 2M PLK1 filtered subset, that had been filtered using the Library Analysis workflow, and prepared using the Create Shape Data File workflow

# Module 6.1 DISE-Like Selection of SBVS and LBVS Hits

* DISE: DIrected Sphere Exclusion (DISE)-like selection of ordered compounds is often used as a post-screening analysis tool. 2003 paper from Anadys Pharmaceuticals describes “Directed Sphere Exclusion (DISE), a modification of the Sphere Exclusion algorithm, which retains all positive properties of the Sphere Exclusion algorithm but generates a more even distribution of the selected compounds in the chemical space. In addition, the computational requirement is significantly reduced, thus it can be applied to very large data sets.

In this section, structure-based and ligand-based prospective screens we ran earlier have to be completed. 
We here used DISE like selection of ordered compounds are often used to balance the tension between “best score” and “chemical diversity”. The premise is that a “novel” candidate compound is potentially more valuable than a “degenerate” candidate of roughly equal score. 

Here we reduced the ~100,000 compounds to top scoring 1000 hits for both SBVS and LBVS

Here our aim is to increase the structural diversity of the 1000 hits. To do that we used dise_select.py, first 100 compounds were used as seed and the compounds come after 100 comparing with fingerprint of seed compounds. and if a compound is considered distinct from the 100 seed compounds based on fingerprint similarity, it will be added to the output list until either 1000 compounds are kept or the input list is exhausted.

# Module 6.2a Inspection, Clustering and Strain Rescoring of SBVS Results

we inspected the DISE-like selection structure files created in the Module 6.1 tutorial from the Active Learning Glide (structure-based) prospective screen. We assessed the diversity and then clustered the compounds to reduce the number of hits, then we re-scored these compounds by running a strain energy calculation in order to identify the best hits to take forward for more in-depth analyses. From the analysis from this step we got 200 representative hits (similarity threshold 0.6, 0.3, 0.145). We ranked these hits groups based on their strain docking score.

# Module 6.2b Inspection, Clustering and Strain Rescoring of LBVS Results

we have inspected the Shape Screen (ligand-based) results that were filtered for diversity using the DISE-like selection script. We inspected the results of groups of 1000 compounds with varying levels of diversity. The compounds were then clustered to create a list of 200. representative compounds for each group. Each group of 200 compounds was additionally assessed in terms of strain energy in order to identify the best hits to take forward for more in-depth analyses.


# Module 6.3 Rank Comparison and Consensus Scoring 
# Module 7.1 Methods for further Evaluating and Enriching Hits
# Module 8 AmpC Case Study








