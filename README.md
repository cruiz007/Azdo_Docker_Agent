# Azdo_Docker_Agent
### Reference: https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops
### Note: This is a repository for the scripts that help build and tag a docker image an microsoft azure devops build agent.
In order to use this script, you would need to familiarize yourself with azdo agent and how they typically work. A few things to consider are:
- Agent pool
- Agent name
- Agent capabilities (Here is where the code can be modified to fit your needs)
- Azdo url
- Personal Access Token(PAT)
- Agent work folder
- check for the 
## Build:
1. Clone repository into your preferred host(where you intend to run docker). Alternatively, you can download zip and used the unziped file.
2. Buid the image using docker `build --tag "azp-agent:linux" --file "./azp-agent-linux.dockerfile" .`
