# delegate-topic-bot

## Usage

For updating the garden windows team Slack bot in the #pcf-windows and garden-windows-bots channels.

1. Go into the config directory and edit the following files: 
* garden-windows.yml
* garden-windows-teams.yml

2. In garden-windows.yml, add a new line in the `Users` section with the name as found in [Pairist](https://pair.ist/garden-windows/current). 
After the name, add the user's `User Id` from Slack. To get the `User Id`:
* Inside the Pivotal Slack Workspace, navigate to the user profile for this new team member and in the url you should see this at the end of the path: `team/USER_ID/`.

The format of the new entry should be:
`<New-User-Name>: <User-Id-From-Slack>`

3. In garden-windows-team.yml, add a new entry under `Union` with the name as found in [Pairist](https://pair.ist/garden-windows/current). 
After the name, add the user's `User Id` from Step 2.:

The format of the new entry should be:
`- user: { id: &<New-User-Name> <User-Id-From-Slack> }`

4. Commit and push changes to Github (make sure you're pushing to the garden-windows branch!!)

5. Go to [delegate-bot pipeline](https://garden-windows.ci.cf-app.com/teams/main/pipelines/delegate-bot) and run the deploy job.
