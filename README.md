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
## Build
1. Clone repository into your preferred host(where you intend to run docker). Alternatively, you can download zip and used the unziped file.
2. Build the image using docker `build --tag "azdo-agent:linux" --file "./azp-agent-linux.dockerfile" .`
3. Check docker images to confirm build and tagging was done `Docker images`
4. The image should be tagged as azdo-agent:linux
- <img width="624" alt="image" src="https://github.com/user-attachments/assets/a2d91327-54a0-4b60-a7a3-c50778a1c041" />
## Run
1. Start the container using the tagged image by running the `Docker run` command below
2. Run the docker command and replace all arguments (<>) with yours. If you need help with this, refer back to the article and learn about the 
    ```docker run -e AZP_URL="<Azure DevOps instance>" -e AZP_TOKEN="<Personal Access Token>" -e AZP_POOL="<Agent Pool Name>" -e AZP_AGENT_NAME="Docker AzdoAgent - Linux" --name "azp-agent-linux" azdo-agent:linux ```
3. Agent should now be running
-  <img width="764" alt="image" src="https://github.com/user-attachments/assets/b90025bc-f012-4b47-a820-914974e2637c" />

## Test 
1. Navigate to your azure devops repository
2. Navigate to organization setting
3. open agent pool you selected when Running the pipeline
4. NAvigate to aents and confirm that an agent with the name `azp-agent-linux` is running and available
