# Regulation of MAVS Expression and Signaling Function in the Antiviral Innate Immune Response

## Intro
- The [[Innate Immune System]] is the first line of defense against pathogens.
	- Their cells express specific pattern-recognition receptors to recognize microbial components
- Among viral components, double-stranded RNA (dsRNA) and single-stranded RNA (ssRNA) are recognized by TLR3,7/8
- RLRs bind dsRNA and trigger antiviral response
- The RLR family has 3 members:
	1. Retinoic acid-inducible gene I (RIG-I)
	2. Melanoma differentiation-associated gene 5 (MDA5)
		- RIG-I and MDA5 are pattern recognition receptors
	3. Laboratory of genetics and physiology protein 2 (LGP2)
		- LGP2 is a regulator of RIG-I and MDA5 mediated signal transduction
- RIG-I (and MDA5) interact with mitochondrial antiviral-signaling protein (MAVS)
	- This induces activation of the TFs interferon regulatory factors (IRF3/7) and nuclear transcription factor-κB (NF-κB)
## Structure and Function of MAVS
- 540-amino acid protein
- Encoded by the nuclear genome
- Is mainly localized on the mitochondrial outer membrane
	- Also detected on peroxisome and mitochondrial-associated endoplasmic reticulum membrane
- 3 domains:
	1. N-terminal caspase recruitment domain (CARD)
	2. Middle proline-rich region (PRR)
	3. C-terminal transmembrane (TM) domain
- MAVS CARD binds to similar CARD present in RIG-I and MDA5, which induces MAVS activation
- After binding to viral components, RIG-I undergoes a conformational change
	1. Exposes their N-terminal tandem CARDs and forms the tetramer via CARDs to be modified with K63-polyubiquitin chains 
	2. K63-linked ubiquitination promotes binding of RIG-I (and MDA5) to MAVS via their CARDs 
	3. MAVS CARD rapidly forms prion-like aggregates, which convert other MAVS on the mitochondrial outer membrane into prion-like aggregates
	4. MAVS binds through its PRR domain of TRAF 2//5/OR 6 which promotes activation of IKK (alpha/beta) complex. 
	5. The complex activates NF-κB to promote the transcription of proinflammatory cytokines
## Regulation of MAVS activity under physiological conditions and during viral infection
- Expression and function of MAVS are tightly regulated at the post-transcriptional and post-translational levels
	- Ensures that RLR signaling pathways are not only rapidly activated upon viral recognition but also curtailed in a timely manner upon viral clearance to avoid potentially harmful tissue damage
### Post-transcriptional Regulation of MAVS
- MAVS mRNA is polycistronic
	- Polycistron= Protein translation can start from internal methionine besides N-terminal methionine
		- Thus, encodes for isoforms by alternative translation of distinct start sites
- MAVS mRNA identified to produce full-length (FL) and 5 CARD-deleted proteins
- Binding of truncated MAVS isoforms to FL MAVS inhibits its spontaneous aggregation
	- Formed aggregates are degraded by mitochondrial autophagy
		- Thereby maintaining autoimmune homeostasis
- MAVS-M142 cannot prevent the aggregation of FL MAVS during viral infection, but can block the production of IFN after MAVS-M142 binding to TRAF
	- Regulation can be achieved by an upstream open reading frame (uORF) in the 5' untranslated region (UTR)
- Outcome of MAVS signaling is dictated to a certain extent by the net effects of of FL MAVS and MAVS truncated isoforms
### Post-translational Regulation of MAVS
- MAVS can undergo a number of post-translational modifications that influence its function in promoting innate immune responses
![[MAVS Table 1.png]]
##### Post-transcriptional Positive Regulation of MAVS
- TRIM31-mediated MAVS aggregation does not occur under RIG-I deficient or non-viral infection conditions
	- Can be considered that RIG-I engagement is required for TRIM31-mediated MAVS aggregation after viral infection
- Viral infection increases glucose metabolism in the host cells, including activation of the hexosamine biosynthesis pathway and elevation of OGT levels
- Phosphorylation is another PTM
- MAVS signaling is regulated via 3 main PTM that act in concert:
	1. TRIM31-mediated K63-linked ubiquitination activates MAVS
	2. TRIM21-mediated K27-linked ubiquitination promotes recruitment of TBK1 to MAVS
		- Enhances downstream signal
	3. TBK1- and IKK-mediated MAVS phosphorylation promotes the recruitment of IRF3 to MAVS
		- Recruited IRF3 is then phosphorylated by TBK1
			- Induces IRF3 homodimerization, translocation to the nucleus, and promotion of IFN recruitment 
- K48-linked ubiquitination and degradation is necessary to maintain an adequate cellular level of MAVS
	- Endogenous protein cyclophilin A is upregulated by viral infection
	- It competes for MAVS binding with TRIM25, and its upregulation inhibits TRIM25-mediated MAVS ubiquitination and degradation
- Ubiquitination is reversible
	- Viral infection leads to upregulations of proteins that removes K48-linked ubiquitination from MAVS to reduce its degradation
##### Post-transcriptional Negative Regulation of MAVS
- Mainly K48-linked ubiquitination modification, signal blocking, autophagy, and apoptosis
###### MAVS Regulation by Ubiquitination
- Binding of various adaptor proteins to MAVS modulates its ubiquitination-mediated degradation
	- I.e.:
		- Poly C-binding protein 2 (PCBP2) is upregulated after viral infection
		- PCBP1 has similar role but expression is not altered by viral infection
			- PBCB1-mediated promotion of degradation is under physiological conditions
			- PCBB2 does the same, but under viral conditions to re-establish homeostasis and avoid excessive immune signaling
###### MAVS blockade via direct protein interaction
- Direct binding of TTLL12 (tubulin-tyrosine ligase-like protein 12) to MAVS, TBK1, and IKKε
	- Expression reduced during viral infection, thereby releasing the block in MAVS-mediated activation of the immune response
- Lactate acts as a key (-) regulator of RLR signaling via direct binding to the MAVS TM domain
	- Thus prevents MAVS mitochondrial localization, aggregate formation, and signaling function
	- Lactate has long been considered metabolic waste product of anaerobic glycolysis
- Binding of activated RIG-I to MAVS causes dissociation of HK2 (hexokinase II), leading to a reduction in glycolysis and lactate production, attenuation of lactate-mediated MAVS inhibition, and upregulation of downstream signaling for IFN production
###### MAVS Regulation related to apoptosis and autophagy
- When other mechanisms fail, apoptosis can be used as a strategy to inhibit viral replication.
- However, the cell has also evolved various feedback mechanisms to ensure timely inhibition of immune signaling to avoid excessive tissue damage
	- NLRP11 (IFN I-induced Nod-like receptor) is upregulated after viral infection and can inhibit type I IFN production. 
- NLRP11 strongly interacts with TRAF6 and promotes k48-linked ubiquitination degradation of TRAF6, thereby inhibiting RLR signaling
	- TRAF6 is involved in apoptosis after viral infection
		- NLRP11 can potentially inhibit apoptosis, ensuring survival of the host cells
- Autophagy, a cellular degradation process, acts as an antiviral defense mechanism by clearing intracellular micro-organisms and interacting with the innate immune response
- Tetherin is IFN-induced membrane protein that is upregulated following viral infection
	- Induced K27-linked ubiquitination of MAVS and, through additional binding, leads to lysosomal degradation
		- Can be considered another negative feedback mechanism that suppresses excessive signaling
- MAVS-mediated antiviral immunity include MAVS phosphorylation and induces MAVS degradation
## Regulation of MAVS by viral proteins
### Cleavage of MAVS
### Degradation of MAVS
### Modulation of MAVS Signaling
## Conclusion

