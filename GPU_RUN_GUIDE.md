# GPU run guide

Use a fresh Colab GPU runtime and run Assignment1_FV.ipynb from top to bottom.

1. Run the install cell once. If Colab requests a restart, restart the runtime
   and continue from the version-check cell.
2. Run Steps 1–3 and check that the reported BS downtilt is positive.
3. Run Step 4. Do not bypass the LoS/NLoS or 80% valid-path checks. They protect
   the later results from a bad geometry.
4. Run Steps 5–7. The learned weights are saved as
   learned_estimators_v3.pt.
5. For a quick receiver smoke test, set FULL_LINK_RUN = False in Step 8.
   Set it back to True for the final BLER and goodput figures.
6. Run Step 9. It creates the second BS-location dataset before evaluating
   site mismatch.

Generated cache files:

- siteA_channels_v3_4x4.pt
- siteB_channels_v3_4x4.pt
- learned_estimators_v3.pt
- link_results_v3.pt

If the BS position, UE grid, solver settings, carrier frequency, SCS or resource
grid is changed, delete the two site cache files and regenerate them.

The notebook intentionally contains no saved numerical output. Save a new copy
after the full GPU run so all report tables and figures come from the corrected
code.
