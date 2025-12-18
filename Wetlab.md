# Fiber-Seq with Hia5 Methylation Protocol

## Cell Growth and Crosslinking

1. **Grow cells**: 50 mL culture to OD₆₀₀ ~0.8
   - Expected yield: ~5 μg DNA (sufficient for 5 reactions)

2. **Crosslink**: Add formaldehyde to 1% final concentration
   - Stir at room temperature for 30 min

3. **Quench**: Add glycine to 125 mM final concentration
   - Stir at room temperature for 5 min

4. **Harvest cells**:
   - Spin down cells, discard supernatant
   - Wash 1× with sterile water
   - Spin down again, discard supernatant
   - Freeze pellet in liquid nitrogen and store at -80°C
   - *Optional*: Freeze in 10 mL aliquots (1 reaction each) and adjust spheroplasting volumes accordingly
   - *Alternative*: Skip freezing and proceed directly to spheroplasting

---

## Spheroplasting

5. **Prepare Buffer Z** (make fresh or prepare stock):
   ```
   25.54 g sorbitol
   12.5 mL 1 M Tris pH 7.4
   Water to 250 mL final volume
   Autoclave or filter sterilize
   ```

6. **Resuspend cells**: 20 mL Buffer Z (for 50 mL pellet)

7. **Add spheroplasting reagents**:
   - 14 μL β-mercaptoethanol (β-ME), vortex
   - 500 μL zymolyase (10 mg/mL in Buffer Z)
     - Source: Sunrise Science Products #N0766391

8. **Incubate**: 25°C with shaking for 30 min
   - Check for spheroplast formation under microscope

9. **Wash spheroplasts**:
   - Spin at 1,500 rpm, 4°C, 6 min
   - Wash 1× in NP buffer
   - Spin as above

**NP Buffer** (store at -20°C, keep on ice during use):
```
1 M sorbitol
15 mM Tris pH 7.4
15 mM NaCl
60 mM KCl
1 mM EDTA
0.5 mM EGTA
0.5 mM spermidine
0.1% NP-40
```

10. **Resuspend**: Pellets in NP buffer to 500 μL final volume

---

## Hia5 Methylation Reaction

11. **Set up Hia5 reactions** (per reaction):
    ```
    Extract (spheroplasts)     100.0 μL
    SAM (NEB #B9003S)           2.5 μL
    Hia5 (100 U/μL)             1.0 μL
    Water                       46.5 μL
    Total                      150.0 μL
    ```

12. **Incubate**: 25°C for 1 h

13. **Heat inactivate**: 65°C for 20 min

---

## Proteinase K Digestion

14. **Add to each reaction**:
    ```
    NP buffer                 320 μL
    20% SDS                    20 μL
    Proteinase K (20 mg/mL)    10 μL
    ```

15. **Incubate**: 65°C overnight

---

## DNA Recovery

16. **Phenol-chloroform extraction**:
    - Add 55 μL 3 M ammonium acetate
    - Add 500 μL phenol/chloroform/isoamyl alcohol
    - Invert to mix
    - Spin at maximum speed, 5 min, room temperature
    - Transfer top (aqueous) layer to new tube

17. **Isopropanol precipitation**:
    - Add 400 μL isopropanol to aqueous layer
    - Invert to mix
    - Incubate at -20°C for ≥20 min
    - Spin at maximum speed, 4°C, 10 min

18. **Wash pellet**:
    - Remove supernatant
    - Wash pellet with 70% ethanol
    - Brief spin at 4°C
    - Remove supernatant, air dry

---

## RNase Treatment

19. **RNase digestion**:
    - Resuspend pellet in 250 μL TE/RNase A
      - (990 μL TE + 10 μL RNase A)
    - Incubate at 37°C for ~1 h

20. **Ethanol precipitation**:
    - Add 25 μL 3 M sodium acetate
    - Add 625 μL 100% ethanol
    - Invert to mix
    - Incubate at -20°C for ≥20 min
    - Spin at maximum speed, 4°C, 10 min

21. **Final wash**:
    - Remove supernatant
    - Wash pellet with 70% ethanol
    - Remove supernatant, air dry
    - Resuspend pellets in 10 μL TE

22. **Quantify**: Measure DNA concentration by Qubit

---

## Methylation Verification (QC)

23. **DpnI digestion** (to confirm methylation):
    ```
    DNA (50-100 ng)
    rCutSmart Buffer         2 μL
    DpnI                     1 μL
    Water                    to 20 μL
    ```
    
    - Incubate at 37°C for 1 h
    - Run on ~0.7% agarose gel
    - **Expected result**: Smear of DNA fragments (indicates methylation)
    - **Note**: DpnI cuts methylated DNA; DpnII does not cut methylated DNA

---

## Library Preparation and Sequencing

24. **Prepare libraries**:
    - Use Oxford Nanopore Rapid Sequencing DNA V14 Barcoding Kit (SQK-RBK114.24)
    - **Step 10 modification**: Use HALF the recommended volume of AMPure XP beads to reduce short reads (<1 kb)

25. **Sequence**: Load at least 4 samples per run

---

## Notes
- **Starting material**: 50 mL pellet at OD₆₀₀ 0.8 = ~5 μg DNA = 5 reactions
- **Hia5 concentration**: Determined to be 100 U/μL (Stergachis lab preparation)
- **Bead selection**: Half-volume AMPure XP enriches for longer fragments
