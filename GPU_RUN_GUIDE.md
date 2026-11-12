# GPU run guide

Use a fresh Colab GPU runtime and run Assignment1_FV.ipynb from top to bottom.

1. Run the install cell once. If Colab requests a restart, restart the runtime
   and continue from the version-check cell.
2. Run Steps 1–3. Confirm the roof anchor `[266.734, 130.195, 49.5552]`,
   5 m mast, UE centre `[20, 283]`, 300 m region, 961 raw candidates, and a
   positive BS downtilt (about 9.59 degrees with Sionna 2.2).
3. Run Step 4. The geometry check should report 33 LoS and 438 NLoS
   non-buffer locations before ray tracing. Do not bypass the LoS/NLoS or 80%
   valid-path checks; they protect the later results from a bad geometry.
4. Run Steps 5–7. The learned weights are saved as
   learned_estimators_v4.pt.
5. For a quick receiver smoke test, set FULL_LINK_RUN = False in Step 8.
   Set it back to True for the final BLER and goodput figures.
6. Run Step 9. It creates the second BS-location dataset before evaluating
   site mismatch.

Generated cache files:

- siteA_channels_v4_4x4.pt
- siteB_channels_v4_4x4.pt
- learned_estimators_v4.pt
- link_results_v4.pt

The v4 channel caches include the BS position and UE-grid geometry in their
metadata. If the geometry, solver, carrier, SCS, or resource grid is changed,
use fresh cache names and regenerate all downstream files.

The notebook intentionally contains no saved numerical output. Save a new copy
after the full GPU run so all report tables and figures come from the corrected
code.
