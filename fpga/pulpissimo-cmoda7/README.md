# PULPissimo on the Digilent Cmod-A7 Board

Solution for the following error:

ERROR: [Synth 8-9123] an enum variable may only be assigned the same enum typed variable or one of its values [/home/declan/pulpissimo/.bender/git/checkouts/pulp_soc-b7e7c62781de8fd8/rtl/pulp_soc/soc_interconnect.sv:277]

After make scripts:

Navigate to .bender/git/checkouts/axi-e89d8332adabf5a9/src/axi_pkg.sv
Before Line 388 add the following:
MY_CUT        = MuxAw | MuxAr | MuxW,

Navigate to .bender/git/checkouts/pulp_soc-b7e7c62781de8fd8/rtl/pulp_soc/soc_interconnect.sv
Modify Line 277 with the following:
LatencyMode: axi_pkg::MY_CUT,
