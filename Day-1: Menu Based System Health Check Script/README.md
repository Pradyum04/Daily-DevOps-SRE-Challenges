### Day-1 Challenge: Menu based System Health Check Script ###
## Objective: Your task today is to develop a menu-driven script that performs essential system health checks. This tool should allow users to select from the following options:
1. Check Disk Usage
2. Monitor Running Services
3. Assess Memory Usage
4. Evaluate CPU Usage
5. Send a Comprehensive Report via Email Every Four Hours

### Solution:
** Pre-requisite **
i. Use a linux environment-(I used AWS 
* Approch-1: Using Python *

  Steps:
  1. Connect the EC2 instance with the local PC
     command: ssh -i ~/Downloads/mykey.pem ubuntu@<PUBLIC_IP>
     
  2. Update & install basics:
     sudo apt update && sudo apt upgrade -y
     sudo apt install -y git curl build-essential python3-dev python3-venv
     
  3. Create the project directory and push the workflow:
     (Run the following commands on EC2 shell where it is connected on local terminal)
     mkdir -p ~/system-health-check
     cd ~/system-health-check

  4. Creating a virtual environment and installing all the required dependencies
     Paste this code(one by one)
     cd ~/system-health-check
     python3 -m venv venv
     source venv/bin/activate
     pip install --upgrade pip
     pip install psutil
     # (optionally boto3 if you want to use SES API)
     pip install boto3

  5. Creating a python script:
     nano healthcheck.py


     

  
