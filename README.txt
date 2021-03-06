Hello!

First, you will want to make a plots folders

>>mkdir plots
>>mkdir plots/png
>>mkdir plots/pdf

Now, you will want to make the data folders

>>mkdir data
>>mkdir data/skimmedFiles
>>mkdir data/hiforest
>>mkdir data/dataColumns

If you have the data-skimmed-file, put it in "data/skimmedFiles"

Beomgon's original data skimming script is "skimmer/forest2diJetSkim_pp5.C".

Run the "runForest2DijetSkimer_GEN.sh". This bash script uses "skimmer/forest2diJetSkim_pp6_genPreSelect.C". Look inside this file for detailed comments. It will give you a skimmed-hiforest that only has gen jets that pass these cuts:

1. Only two gen jets are in the event.
2. The leading jet has genpt > 20 GeV.
3. The subleading jet has genpt > 15 GeV.
4. Both genjets have abs(geneta) < 1.8
5. The phi difference between the genjets is > 2. 
6. The invariant mass of the gen dijet is > 35 GeV.

Now, with this hiforest that only has what we want in it, run the "runForest2DijetSkimer_MC.sh". Look inside this file for detailed comments. This bash script uses "skimmer/forest2diJetSkim_pp6.C".

Descriptions of plotting scripts used to create the plots in the google doc of preapproval-answers:

1. ang_resolution.C: 
	plots the angular resolution of jets, for coherent dijet selection. Uses skim file as input.
2. pt_resolution.C: 
	plots the pt resolution of jets, for coherent dijet selection.  Uses skim file as input.
3. qt_gaussian.C:
	gaussian fit to the QT distribution, for the coherent dijet selection. Uses data columns as input.
4. v2_v2Raw_qtRaw.C:
	comparison of v2, v2raw, and v2 gen for the coherent dijet selection. Uses data columns as input.
5. qt_gaussian_raw.C:
	gaussian fit to the raw QT distribution, for the coherent dijet selection. Uses data columns as input.
6. vertex_mcreco_data.C:
	difference between reco and gen vertices, coherent dijet selection. Uses data columns as input.
