# Regulation of [[RIG-I]]-like receptor-mediated signaling: interaction between host and viral factors

## Intro
- IFNs (interferons), first discovered family of cytokines, were identified as host factors secreted by virus-infected cells to "interfere" with viral replication
	- Further classified into 3 types in humans:
		1. type I IFNs: IFNα forms (1, 2, 4-8, 10, 13, 14, 16, 17, 21), IFNβ, IIFNω, IFNε, and IFNκ
		2. type II IFNs (IFNγ)
		3. type III IFNs (IFNλ1-4)
	- Type I and III IFNs play essential roles in innate immunity
	- Type I IFN secretion induced by microbes:
		1. Type I IFN receptor complex and surrounding noninfected cells, thereby activating cytoplasmic Janus kinases (JAK1 and TYK2)
		2. JAK-mediated tyrosine phosphorylation activates STAT1&2
		3. STAT1&2 with DNA-binding component IRF (IFN regulatory factor)-9 form a tripartite complex called ISGF3 (IFN stimulated gene factor 3)
		4. ISGF3 is translocated to the nucleus
		5. ISGF3 binds to ISRE (IFN-stimulated response element) on the promoters of hundreds of ISGs (IFN-inducible genes) and activates their transcription
		6. Proteins encoded by ISGs induce strong antiviral innate immunity to eliminate invading viruses
	- Type III IFNs are also activated in response to pathogenic infections
		- However, these cytokines are recognized by a distinct receptor complex made up of IFNLR1 and interleukin (IL)-10R2
			- Downstream signaling pathway is nearly identical to type I IFNs
				- Results in similar antiviral activity via JAK-STAT-induced ISG production
					- Functional different might be caused cell-type specificity producing IFNs and their receptors. 
						- Type III IFN receptors are predominantly expressed on epithelial cells and certain myeloid cells
- Infections detected by PRRs:
	- dsRNA: TLR3
	- ssRNA: TLR7&8
	- unmethylated CpG DNA: TLR9
	- Cytosolic RNAs: RLRs
	- cytosolic DNA: cGAS
- TFs IRF3-7 and NF-κB downstream of IFN-inducing PRRs are commonly activated and transiently induce IFN-encoding genes
## Activation of RLR-Mediated Signaling
### Association Between RLRs and MAVS
- 3 RLRs are ubiquitously expressed in the cytoplasm
- RIG-I detects substrate RNAs that have a panhandle double-stranded structure with a 5′-triphosphate or 5′-diphosphate moiety and activates downstream signaling in an ATP-dependent manner
- MAVs-mediated signaling is required to increase cell membrane permeability and the subsequent K+ ion efflux that leads to the formation of the NLrP3-containing inflammasome
### Activation of RLR-mediated signaling
- In steady state, RIG-I adopts an auto-repressed conformation
### Intracellular localization of RLRs and MAVs
- In the inactivated state, RLRs are uniformly expressed in the cytoplasm
- MAVs is also localized in MAMs (mitochondrial-associated endoplasmic reticulum membranes) and peroxisomes and regulates RLR-mediated signaling
-  Stress granules (SGs) are membrane-less cytoplasmic aggregates to which RLRs are localized
	- Can enhance MAVs-mediated signaling by acting as platforms for the recognition of foreign viral RNAs by RLRs
	- Under various stress conditions (i.e. viral infection) cells produce SGs to inhibit cellular protein synthesis and store the protein machinery to reinitiate translation after recovery from the stress condition.
		- Machinery= Translationally stalled mRNAs and RNA-binding proteins
- Accumulation of MAVs-enriched mitochondria around RIG-I containing aggregates supports the hypothesis that SGs serve as platforms for viral detection
### RLRs and their involvement in autoimmune and autoinflammatory diseases
- SNPs in DDX58 (encodes RIG-I) associated with Singleton-Merten syndrome (SMS).
- Other mutants associated with SMS (devoid of ATP-independent activity) interact with endogenous ribosomal RNA and activate unintentional ATP-independent IFN production, resulting in SMS development
	- [[Endogenous RNA recognition]]
	- [[ATP hydrolysis and Endogenous RNA]]
## Regulation of RLR-mediated Signaling by RNA recognition
### RNA recognition by RIG-I
- Substrate specificity for RNA recognition by RIG-I clearly shows that the 5'-cap and [[5′-monophosphate RNA]] structures of endogenous RNAs (i.e. mRNA, tRNA, rRNA) can NOT be recognized by RIG-I
- In addition to 5'cap, 2'O-methylation at +1 base neighbor of 5'cap (N1 position) is critical for evading RIG-I recognition
	- Changing the His830 residue with Ala enhanced IFN production via 2'O-methylated endogenous mRNA recognition
		- His830 residue of the RIG-I RNA-binding pocket is critical for distinguishing the 2'O-methylated RNA at N1 site
### Interactions between RIG-I and endogenous RNAs
- Since 5' triphosphate (5'ppp) signature in host RNAs is apparent during transcription by RNA polymerases, RIG-I can recognize host endogenous RNA
	-  5'ppp RNA transcribed by RNA polymerase III from intracellular poly(dA-dT) DNA can induce IFNs via RIG-I (shown in response to dsDNA)
- NGS of RNA samples interacting with RIG-I during herpes simplex virus infection led to identification of endogenous RNA transcribed from 5S ribosomal RNA pseudogene 141, which then is translocated from the nucleus to the cytoplasm to activate RIG-I mediated signaling
	- **Activation of the RIG-I pathway via pol III-induced endogenous RNA is a critical host strategy to fight against DNA virus infections**
- 7SL RNA is a signal recognition particle component that is upregulated in stromal cells by Notch-Myc signaling from breast cancer cells
	- Excess of 7SL RNA is secreted in exosomes, which in turn activates RIG-I in breast cancer cells
- Mouse-specific lnc-Lsm3b and human-specific lncATV, which are upregulated by viral infection, compete with viral RNAs for detection by RIG-I, thereby inhibiting RIG-I-mediated IFN production
- microRNAs involved in posttranscriptional regulation are believed to be unrecognized by RIG-I, as they do not contain 5′-triphosphate and have a 3′-overhang.
	- **However, several miRNAs enriched in uridines are potential RIG-I agonists.**
		- miR136, the expression of which is induced by IAV infection, can inhibit IAV growth by activating RIG-I-mediated signals
		- introduction of exogenous circular RNAs (circRNAs) into cells can activate RIG-I in a 5′-triphosphate- or double-stranded structure-independent manner
- Several reports have also demonstrated that contaminating short ssRNAs generated during the production of circRNAs are critical for circRNA-mediated RIG-I activation
	- Normally endogenous circRNAs, generated by back-splicing to covalently link the 3′ and 5′ ends of the RNA exon, avoid RIG-I recognition by exhibiting N6-methyladenosine modification
- Based on accumulating evidence highlighting the physiological significance and molecular machinery of RIG-I-mediated signaling, research on the agonist/antagonist targeting of RIG-I has been initiated
	- 5′-triphosphate dsRNA has been shown to exhibit antiviral activity against lethal IAV infection
	- Unique RIG-I agonist has been reported to exhibit significant antitumor activity
	- RIG-I antagonists have also been identified with the aim of controlling excessive IFN production
## Regulation by Host Proteins
### Regulation by ubiquitin ligases and deubiquitinases
- Post translational modifications plays an essential role in regulating RLR/MAVs-mediated signaling
### Regulation by other host proteins
- 14-3-3 proteins including 14-3-3ε and 14-3-3η can function as mitochondrial transporting chaperones
- NS3 proteins antagonize RLR-mediated signaling by sequestrating 14-3-3 proteins
- Zyxin, involved in actin polymerization
	- Localizes with MAVs on the mitochondria and functions as a scaffold protein for the interaction between RLRs and MAvs
- SIDT2, a dsRNA transporter protein, enhances RLR signaling by enhancing the transport of internalized dsRNA from endosomal compartments to the cytoplasm for viral detection by RLRs.