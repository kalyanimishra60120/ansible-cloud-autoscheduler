# Ansible EC2 AutoScheduler

**Automated Cost Optimization on AWS Using Ansible**

This project automatically **starts** and **stops** AWS EC2 instances based on tags — helping reduce cloud costs for non-production environments such as dev, test, staging, and labs.  
It demonstrates real-world Infrastructure Automation, Cost Governance, and Infrastructure-as-Code practices.

---

## ✅ Features

- 🔁 Automatically **start** / **stop** tagged EC2 instances
- ⏱️ Can be scheduled using **cron** (automation-ready)
- 💵 Reduce AWS cost for idle resources
- 🧠 Uses tag-based filtering for easy grouping
- 🧰 Fully built in **Ansible**
- 🏷️ Infrastructure-as-Code (IaC) principles
- 🛡️ Idempotent (safe to re-run)

---

## 🏛 Architecture

+-------------------------+
| Developer Machine       |
|                         |
|                         |
|  +-------------------+  |
|  | Ansible Playbooks |  |
|  +---------+---------+  |
|            |            |
+------------|------------+
             |
             | AWS SDK via boto3
             v
+-------------------------------+
| AWS EC2                       |
|                               |
|  +-------------------------+  |
|  | Tagged EC2 Instances    |  |
|  | (AnsibleManaged=True)   |  |
|  +-------------------------+  |
+-------------------------------+

## Usage

1. Activate virtual environment: `source venv/bin/activate`
2. Run start playbook: `ansible-playbook start_ec2.yml`
3. Run stop playbook: `ansible-playbook stop_ec2.yml`

## Notes

- Ensure your EC2 instances have the tag `example-xyz`
- Region can be updated in the playbooks
- This project demonstrates cloud automation and cost optimization

## Prerequisites
- Python 3
- Ansible
- boto3 & botocore installed in a virtual environment
- AWS CLI configured with valid credentials
- (commands) - ### Setup Virtual Environment
                   - python3 -m venv venv
                   - source venv/bin/activate

### Install Dependencies
pip install -r requirements.txt
ansible-galaxy collection install -r requirements.yml


## Cost-Optimization Impact
If your dev environment costs ₹8/hour:
| State          | Hours/Day | Monthly Cost |
| -------------- | --------- | ------------ |
| Always running | 24        | ₹5760        |
| Automated      | 10        | ₹2400        |
~58% savings — at scale this matters a lot.







