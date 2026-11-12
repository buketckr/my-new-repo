# GPU run guide

1. Open Assignment1_FV.ipynb in Colab.
2. Select Runtime → Change runtime type → GPU.
3. Run the installation cell first. If Colab asks for a restart, restart the
   runtime and then continue from the Python-version cell.
4. Run the remaining cells in order.

After Steps 1–3, check these values:

- roof position: [266.734, 130.195, 49.5552]
- mast height: 5 m
- antenna position: [266.734, 130.195, 54.5552]
- UE centre: [20, 283]
- UE area: 300 m × 300 m
- candidate locations: 961
- outdoor locations: 495
- downtilt: about 9.59°

Before the long ray-tracing cell, the geometry check should show 33 LoS and
438 NLoS non-buffer locations.

Step 8 can take a long time. To test the receiver code first, set
FULL_LINK_RUN = False and run the Step 8 cells. For the final results, change
it back to True and rerun Step 8 before continuing to Step 9.

The notebook saves:

- siteA_channels_4x4.pt
- siteB_channels_4x4.pt
- learned_estimators.pt
- link_results.pt

The channel files are reused when the matching geometry is loaded. Start with a
fresh runtime for the first full run. When everything finishes, save the
executed notebook so the tables and figures are included.
