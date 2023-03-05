# ATP hydrolysis by the viral RNA sensor RIG-I prevents unintentional recognition of self-RNA

## Intro
- PRRs (pattern recognition receptors) sense pathogen or danger-associated molecular patterns (PAMPS or DAMPS)
	- Trigger molecular cascade that initiates and orchestrates cellular response through activation or i.e. interferon regulatory factors and NF-κB
- RLRs recognize cytosolic foreign RNA
- RIG-I preferentially detect base paired dsRNA (double-stranded) ends with either 5'ppp or 5'pp (diphosphate) moieties
	- Not 2' OH methylated at the first 5' terminal nucleotide
- RIG-I also detects poly-U/UC-rich dsRNA
- MDA5 ligands not well known, but do include >1000 bp dsRNA, high order dsRNA, or AU-rich RNA
- RLRs are superfamily II (SP2) of ATPases, helicases, or nucleic acid translocases members
- RIG-I and MDA5 consist of 2 N-terminal tandem caspase activation and recruitment domains (2CARD), a central ATPase/translocase domain and C-terminal regulatory domain (RD)
	- When activated, RD binds to the ppp/pp-dsRNA end, while SF2 domain interacts with adjacent RNA duplex and forms active ATPase sites.
	- In this conformation, 2CARD module can be K63-linked polyubiquinated.
	- Multiple Ub-2CARD complexes assemble to form a nucleation site for MAVS polymerization into long helical filaments
- MDA5 doesn't recognize terminal structures, but cooperatively polymerizes along dsRNA which supposedly triggers MAVS polymerization
- The SF2 ATPase domain plays a critical role in RIG-I activation
	- Mutation of the 7 SF2 "helicase" motifs resulted in RLRs that are either inactive or signal constitutively
## Results
### Prevention of ATP hydrolysis in RIG-I leads to a constitutive activation of IFNβ promoter by recognition of self-RNA 
- Dissect influence of mutations on ability of RIG-I to elicit downstream signaling, used IFNβ promoter activity assay
	- Carried out in HEK 293T RIG-I KO cells
- In various KOs and mutation introductions:
	1. Mutated E373Q signaling in non-infected cells because self-RNA interaction? Failed to signal
		- E373Q has a stabilized ATP-bound state by slowed-down ATP hydrolysis
	2. Point mutation in RD? RIG-I E373Q,K888T still constitutively active in non-infected cells
		- K888T mediates ppp binding in RD
			- Mutations in this residue inactivate recognition of viral RNA
		- Indicates increased signaling capacity of endogenous RNA is independent from 'ppp or 'pp-dsRNA epitopes that RIG-I recognizes via RD
### RIG-I ATP hydrolysis defective mutant E373Q shows increased interaction with ribosomal RNA
- IP RIG-I & mutants from noninfected & infected HEK 293T RIG-I KO cells and analyzed copurified RNA molecules
	- RIG-I E373Q has 3x higher RNA recovery than RIG-I regardless of infection or lack thereof.
		- The co-purified RNA isn't immunostimulatory in a RIG-I WT background
			- But cells that transiently express RIG-I E373Q can be further stimulated by transfection of total RNA extracts and purified rRNA
				- Suggests rRNA can activate RIG-I E373Q
- Data suggests RIG-I recognizes immunostimulatory RNA via the SF2 and RD domains, 
	- Does not require ATP binding for this process
	- ATP binding is necessary bc RIG-I K270I expression alone doesn't stimulate the IFNβ promoter
- Purified full-length human RIG-I and RIG-I E373Q and 80S ribosomes to test for direct interaction
	- Verifying higher affinity of the RIG-I ATP hydrolysis defective mutant towards rRNA
		- Confirmed both RIG-I E373Q and RIG-I WT bind ATP, only WT hydrolyzes ATP
- Conducted sedimentation assays with rRNA pre-incubated with WT RIG-I or RIG-I E373Q w/ or w/o ATP or non-hydrolysable ATP analogue ADP-BeF3
### Specificity of RIG-I towards dsRNA is increased in ATP presence
-  Evaluated role of ATP binding and hydrolysis of RIG-I in presence and absence of ATP or ADP-BeF3 w/ different RNAs
	- RNAs mimic different types of endogenous or viral RNAs
- Used fluoresce anisotropy experiments to dissect influence of different RNA ends
	- Positive effect of ATP was not observed when corresponding ppp-dsRNA 12 mer
		- Plausible RIG-I dissociates from unphosphorylated RNA termini w/ an increased rate after ATP hydrolysis than from ppp-termini
- Tested the role of ATP on binding of different RIG-I KOs/mutants to the ES hairpin RNA mimicking the base of ribosomal ES7L.
	- In presence of ATP:
		- Moderately increased binding of RIG-I E373Q and C268F to hairpin
		- ATP reduced affinity of WT RIG-I 
## Discussion
- Mutations that slowed down/inhibited RIG-I ATPase led to increased interaction of RIG-I w/ endogenous RNA
	- Includes dsRNA expansion segments of the human large ribosomal subunit
- Results suggest RIG-I ATPase confers specificity to viral RNA by preventing signaling through abundant background of self-RNA
- Discovered single amino acid mutations that are mostly found within the ATPase domain of RLRs
- Increased interferon levels suggest increased activation of MDA5 or RIG-I underlies the molecular pathology of diseases
- Mutations in E373Q, E373A, and C268F all led to increased activation of RIG-I in no infection
- 

# Experiment Ideas
1. IP RIG-I & mutants from noninfected & infected HEK 293T RIG-I KO cells and analyzed copurified RNA molecules
2. Analyze on Bioanalyzer RNA chip or agarose gel
3. Sedimentation assays via ultra-centrifugation of sucrose cushions loaded with 80S ribosomes
4. EMSA (electrophoretic mobility shift assay)
5. Fluoresce anisotropy experiments to dissect influence of different RNA ends
6. ATP hydrolysis assays