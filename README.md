# emptyInfo om Retension policies
https://learn.microsoft.com/en-us/azure/devops/pipelines/policies/retention?view=azure-devops&tabs=yaml

There are three main levels of retention policies in Azure DevOps: 
global (organization) level, project-level, and pipeline-level.

FAQ
I did not mark runs to be retained indefinitely. However, I see a large number of runs being retained. How can I prevent this?
This could be for one of the following reasons:

The runs are marked by someone in your project to be retained indefinitely.
The runs are consumed by a release, and the release holds a retention lock on these runs. Customize the release retention policy as explained above.

Retention Issue
https://stackoverflow.com/questions/66891132/azure-pipeline-runs-not-automatically-deleting
https://developercommunity.visualstudio.com/t/builds-are-not-removed-after-release-retention-per-1/1661548

Undersök mer: https://tenbulls.co.uk/2020/03/25/delete-old-build-definitions-in-azure-devops/
Undersök retention Lock

Powershell script
(Användaren har skapat ett PowerShell-skript som efterliknar Retention policies.)
https://developercommunity.visualstudio.com/t/Azure-DevOps-Server-2020-Retention-Polic/1306205

Clean up space in database
https://marcusfelling.com/blog/2020/how-to-reduce-the-size-of-your-tfs-azure-devops-server-collection-databases/

Program som Delete:ar: Test runs
https://www.opentechguides.com/how-to/article/azure/207/rest-api-delete-test-run.html

Get Test run med REST-API för att testa först innan delete:
https://learn.microsoft.com/en-us/rest/api/azure/devops/test/runs/get-test-run-by-id?view=azure-devops-rest-7.0&tabs=HTTP

Manuellt Delete:a Test Run med REST-API från ADO:
https://learn.microsoft.com/en-us/rest/api/azure/devops/test/runs/delete?view=azure-devops-rest-7.0&tabs=HTTP

Använd TFSConfig command-line tool  (Delete TestResults)
https://learn.microsoft.com/en-us/azure/devops/server/command-line/tfsconfig-cmd?view=azure-devops-2020#deletetestresults



Undersök olika nivåer av retention. Ärver från varandra? pipeline retention projekt retention osv


