# Useful Links and Instructions

## 📦 Code Repositories

- **Data Validator**  
  [mdw-nl/strata-fit-data-schema](https://github.com/mdw-nl/strata-fit-data-schema)

- **Demo Vantage6 Infrastructure**  
  [mdw-nl/v6-infrastructure-sh](https://github.com/mdw-nl/v6-infrastructure-sh)

- **Partial Stats**  
  [mdw-nl/strata-fit-v6-stats-py](https://github.com/mdw-nl/strata-fit-v6-stats-py)

- **Federated Kaplan-Meier**  
  [mdw-nl/strata-fit-v6-km-py](https://github.com/mdw-nl/strata-fit-v6-km-py)

- **Federated Cox Regression**  
  [mdw-nl/strata-fit-v6-coxph-py](https://github.com/mdw-nl/strata-fit-v6-coxph-py)

- **Federated Logistic Regression**  
  Inherited from: [MaastrichtU-CDS/v6-logistic-regression-py](https://github.com/MaastrichtU-CDS/v6-logistic-regression-py)

- **Federated K-means**  
  To be inherited from: [MaastrichtU-CDS/v6-kmeans-py](https://github.com/MaastrichtU-CDS/v6-kmeans-py)

---

## 🌐 STRATA-FIT Federated Learning for Researchers

- **User Interface**: [https://stratafit.prod.medicaldataworks.nl/](https://stratafit.prod.medicaldataworks.nl/)  
- **API Documentation**: [https://stratafit.prod.medicaldataworks.nl/api](https://stratafit.prod.medicaldataworks.nl/api)

### 🧪 Example Python Client Usage

```python
from vantage6.client import Client
from getpass import getpass

config = {
    'server_url': "https://stratafit.prod.medicaldataworks.nl",
    'server_port': 443,
    'server_api': "/api",
    'username': YOUR_USERNAME,
    'password': getpass("Password: "),
    'mfa_code': getpass("2FA: "),
    'organization_key': YOUR_ENCRYPTION_KEY
}

# Initialize and authenticate client
client = Client(config['server_url'], config['server_port'], config['server_api'])
client.authenticate(config['username'], config['password'], mfa_code=config['mfa_code'])

if config['organization_key']:
    client.setup_encryption(config['organization_key'])
```

### 🚀 Submitting a Federated Task

```python
task_input = {
    'method': YOUR_ALGORITHM_METHOD,
    'kwargs': {
        'param1': VALUE_1,
        'param2': VALUE_2,
    }
}

task = client.task.create(
    collaboration=YOUR_COLLABORATION_ID,
    organizations=[ORG_ID_1, ORG_ID_2, ORG_ID_3],
    name="OPTIONAL_TASK_NAME",
    image="ghcr.io/mdw-nl/strata-fit-v6-ALGORITHM_NAME-py@sha256:ALLOWED_ALGORITHM_HASH",
    description="OPTIONAL_TASK_DESCRIPTION",
    databases=[{'label': YOUR_DATASET_LABEL}],
    input_=task_input
)
```

---

## ⚙️ STRATA-FIT Federated Learning for Node Admins

- **Node Admin Instructions** [https://v6-node-instructions.prod.medicaldataworks.nl](https://v6-node-instructions.prod.medicaldataworks.nl)
