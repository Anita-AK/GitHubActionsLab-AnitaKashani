Workflow 1- Dependent jobs workflow
This workflow demonstrated how jobs can depend on each other. One job needs to complete before the following can begin.
This is done using the 'needs' keyword, where you specify that the current job needs the completion of the previous one before it can start.
This was the workflow build_application > test_application > deploy_application
The build job ran first, then the test job only after the build job finished, and finally the deploy job ran after test had concluded.

Workflow 2 - Independent jobs/Multi-platform jobs
This workflow demonstrated how different jobs can run independently and in parallel, as well as on different operating systems
There were 3 independent jobs running on linux ubuntu, windows os, and mac os. 
Unlike dependent workflows, this workflow did not use the 'needs' key. It still used the 'runs-on' key like workflow 1 to specify the operating system. 
The 'env' key was not used in this workflow, but I understand it is important because it allows workflows to avoid repeating the same values in different places.

Challenges
First challenge was that workflow 1 was not appearing in the actions tab. This is because i incorrectly created it in the root instead of inside .github/workflows. It was quickly corrected, as visible in the screenshots
Second challenge that the first workflow ended up running when the second one was committed. 
The multi-platform workflow was configured to run on pull requests, not direct pushes. Because of this, it did not run until a pull request was created.
This was resolved by creating a new branch, making a small change, and then opening a pull request into the main project branch.
