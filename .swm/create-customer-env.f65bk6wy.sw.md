---
title: Create Customer Env
---
&nbsp;

## 1\. Env data:

To get the data that we need to start creating env we need to get it from the customer success&nbsp;&nbsp;

and then fill this excel with the relevant data to each coloums&nbsp;&nbsp;&nbsp;

<https://docs.google.com/spreadsheets/d/1EJmDjA_mOp070Ey7MNGksbzKJZ9gnoMCdkBKSzAMncU/edit?gid=0#gid=0>

&nbsp;

## 2\. Create a container

Full explanation:   <https://docs.swimm.io/on-prem-agent-installation-guide/?platform=cloudrun>

1. Open google cloud <https://console.cloud.google.com/>
   1. search for secret manger&nbsp;&nbsp;
   2. Click on  "Create secret"&nbsp;&nbsp;
   3. Add the new name, making sure it matches the "V3 Cloud run container name" column exactly &nbsp;
2. &nbsp;
3. **Copy one of the existing configurations that is closest to the new environment, or use this example.**
4. &nbsp;

```yml
 # yaml-language-server: $schema=https://docs.swimm.io/schemas/onprem-agent-config.json

# For configuring On-Prem/Enterprise Git Provider authentication, remove if not used
git:
  provider: <github|gitlab>
  host: <git_server_url>
  oauth:
    clientId: <client_id>
    clientSecret: <client_secret>

# For configuring AI features, remove if not used
ai:
  models:
    short:
      provider: azureOpenAI
      deployment: <gpt-4o-mini-deployment-name>
      model: gpt-4o-mini
    long:
      provider: azureOpenAI
      deployment: <gpt-4o-deployment-name>
      model: gpt-4o
    completion:
      provider: azureOpenAI
      deployment: <gpt-35-turbo-instruct-deployment-name>
      model: gpt-3.5-turbo-instruct

  providers:
    azureOpenAI:
      endpoint: https://<azure-openai-resource>.openai.azure.com
      apiKey: <azure_openai_api_key>
```

<https://docs.swimm.io/on-prem-agent-installation-guide/?platform=cloudrun>

&nbsp;&nbsp;&nbsp;

&nbsp;

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
