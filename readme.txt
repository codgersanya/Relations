Scripts to create relations

X2: TermpointtoENB and ExternalEutrancellFDD: https://github.com/codgersanya/externaleutrancellfdd (incl. Addition of ExternalEutranCellFDDs)
X2NR: TermpointtoGNB:  https://github.com/codgersanya/codgersanya/TermPointtoGNB
XN: TermpointtoEnodeb:  https://github.com/codgersanya/codgersanya/TermpointtoEnodeb

Usage:
1. Choose the relevant script to create freq-relations first then
2. choose one for cell relations

Login to the node and run(x) <any relationscript>
You may run them using mobatch.

Relation-relevant scripts rely on existing frequency MOs, internal and external cell MOs.
These MOs are autocreated upon the relevant termpoint's operational state become enabled -except ExternalEutranCellFdds.
ExternalEutranCellFdds are not autocreated by X2, only by ANR.
To avoid waiting for ANR to create ExternalEutranCellFdds, the externaleutrancellfdd-script creates them manually.
All termpoints-relevant scripts login to the neighbor node(s), fetches all data -needed for creation of the MOs automatically.
Just a list of the wanted termpoints need to be given in as input (e.g. 69012BB2-69013BB2).
Moshell is needed for the 'monode' cmd to work (scripts for termpoints operate with the 'monode' cmd).
~/moshell/sitefiles/ipdatabase must include all nodes with their OAM IP-addresses -for the termpoint scripts to work!

To have all relations:
	1. Run script for termpoint
	2. Run script for freq-relation
	3. Run script for cell relation
	4. For parameter and MOM compliance to the PM, run unsorted_settings.mos
	5. To avoid shooting yourself on foot, run lab-specific_settings.mos (this includes settings suitable for lab purposes -different from the PM).

Note that although XN is not needed for NR-NSA mobility, it's useful for having and keeping neighbor information up-to-date on the nodes.
