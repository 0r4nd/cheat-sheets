# 1. Install [Node.js](https://nodejs.org/en) (LTS version)
# 2. Install VSCode
- **Step 1:** Update the system repository ```sudo apt update```
- **Step 2:** Install Package Dependencies ```sudo apt install software-properties-common apt-transport-https wget -y```
- **Step 3:** Add GPG Key ```wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -```
- **Step 4:** Add Repository ```sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"```
- **Step 5:** Install vscode ```sudo apt install code```
- **Step 6:** Verify Installation ```code --version```
