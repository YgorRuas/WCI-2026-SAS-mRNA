# Learn More: Supplementary Data & Extended Rationale

Welcome to the extended data section of our project. To keep the poster concise and visually engaging, we have compiled all the underlying raw data, 3D renderings, and validation metrics here.

## 🛡️ The Glycan Shielding Challenge
While mRNA vaccines offer a rapid and adaptable platform, expressing bacterial antigens like the *Staphylococcus aureus* ATP synthase subunit alpha (SAS) in mammalian host cells introduces a biological bias: **eukaryotic glycosylation**. 

Bacteria lack the extensive glycosylation machinery of eukaryotes. When mammalian cells translate the vaccine's mRNA, they attach bulky glycans (N- and O-linked) to specific amino acid motifs. This "glycan shield" can sterically block conformational B-cell epitopes, preventing the host immune system from recognizing the protein and producing effective neutralizing antibodies.

## 🎯 Targeted *In Silico* Optimization
Our strategy focused on precision-engineering the SAS sequence to remove these glycan attachment points without disturbing the protein's overall fold. We targeted a highly immunogenic region containing critical threonine residues. By introducing a double substitution (124 T-G and 126 T-G), we achieved the following validated results:

* **N-Glycosylation Neutralized (NetNGlyc 1.0):** The wild-type sequence contained a highly probable N-glycosylation site at Asn122 (motif N-T-T-K, score 0.7843). By mutating Thr124 to Glycine, the essential Asn-X-Ser/Thr consensus motif was broken, completely eliminating this predicted N-glycan site.
* **O-Glycosylation Eliminated (NetOGlyc 4.0):** The native sequence exhibited strong O-glycosylation potential at Thr123, Thr124, and Thr126. The T124G and T126G mutations directly removed two of these acceptors. Furthermore, the local sequence alteration caused the O-glycosylation prediction score for the adjacent Thr123 to drop below the positive threshold (from 0.677 to 0.414), effectively clearing the entire cluster of O-glycans.
* **C-Glycosylation Maintained (NetCGlyc 1.0):** The baseline C-mannosylation profile (site 463) remained perfectly stable and unaffected by the distant mutations.

## 🧬 Structural Validation
Replacing threonines with glycines introduces microflexibility, which could potentially collapse the local secondary structure. However, our metrics confirm the structural integrity was maintained:
* **AlphaFold 3:** The mutated region retained maximum confidence scores (pLDDT = 100), proving the 3D architecture remained completely rigid and stable.
* **DiscoTope 3.0:** Spatial immunogenicity calculations confirmed that the key conformational B-cell epitopes surrounding the mutation site remained fully exposed and statistically viable for antibody recognition.

## 📂 Repository Directories
Explore the raw data and visual renderings that support these findings:

* **[🧬 3D Protein Structures](assets/3D_structures/)** 
  High-resolution renders of the native and mutated SAS antigen, including close-up alignments of the 124/126 mutation sites.
* **[📊 Software Data & Validation Reports](assets/software_data/)** 
  Full prediction outputs from the NetGlyc suite, AlphaFold 3, and DiscoTope 3.0 (CSV and PDF formats).
* **[📄 Original Project Abstract](assets/abstract_WCI.pdf)** 
  The official abstract submitted to the WCI 2026 congress.

---
[⬅️ Return to Main Page](README.md)
