Proposition

Following our discussion of this morning : 

GIT Cloud intitiative is motivated by the following drivers
* Higher availability of GIT for developpers
* More precise definition of the roles & accesses
* New opportunities for Cloud based solutions

Security assessement & Git Cloud providers assessment documented in PLAT-245

It's understood from the discussion of the 23/03/2021 that :

1. GIT Cloud can only host source code and not the configuartion for the production that would remain in the current GitLab
2. If GIT Cloud is selected, a backup process is required and need to answer the following question :   
    * How & when is the backup synched?
    * Do we use the current Gitlab for this
    * How is the backup used in case of disaster?
3. Whatever the solution envisaged, we need to make sure that :
    * Direct commit in master/main is not possible 
    * Each commit(s) is reviewed in merge requests
4. Exit strategy is clear as far as only code is stored

For the selection of providers
* CI/CD capabilities are not envisaged, Jenkins is kept.
* The following ranking is agreed with regards to capabilities (security & rights management) and costs
    1. AWS
    2. Github
    3. Gitlab (too expensive)
    4. BitBucket (not secured enough)
* Azure Git must be assessed in addition to the aforesaid providers

Next action : Agreement to defend the "Materiality" assessment of source code made by Vincent in PLAT-245 => Yannick & Claude
This decision defines the complexity of the compliance to CSSF obligations as well as the timeline of such a setup.

Pre-requisite: Request from Yannick & Claude to have a view of the GIT flows between Developer workstation & Cloud servers => Vincent


