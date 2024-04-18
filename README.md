# demo
##Task  5.1
Репа для завдань  5 тижня

Перше завдання.
Встановлення плагіну:
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)

$ nano ~/.zshrc

Додоається ця строка:
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"

Потім:
$ source ~/.zshrc

$ k krew

$ k krew install ns

Файл з кодом створюється:
$ touch kubeplugin
$ chmod 755 kubeplugin 
$ ls -al kubeplugin  

#TASK 5.3
4. The resulting manifest in the yaml directory in the root of the repository.

| NAME                        | PROMPT                             | DESCRIPTION                                                              | EXAMPLE                                     |
|-----------------------------|------------------------------------|--------------------------------------------------------------------------|---------------------------------------------|
| app.yaml                    | Create Application Config          | YAML to define the basic schema of a Kubernetes application              | [app.yaml](yaml/app.yaml)                 |
| app-livenessProbe.yaml      | Add Liveness Probe                 | YAML to define a liveness probe for your application                    | [app-livenessProbe.yaml](yaml/app-livenessProbe.yaml) |
| app-readinessProbe.yaml     | Add Readiness Probe                | YAML to define a readiness probe for your application                   | [app-readinessProbe.yaml](yaml/app-readinessProbe.yaml) |
| app-volumeMounts.yaml       | Configure Volume Mounts            | YAML to define and configure storage volumes for your application       | [app-volumeMounts.yaml](yaml/app-volumeMounts.yaml) |
| app-cronjob.yaml            | Create Cron Job                    | YAML to define a cron job within your application                       | [app-cronjob.yaml](yaml/app-cronjob.yaml) |
| app-job.yaml                | Create a Job                       | YAML to define a job within your application                            | [app-job.yaml](yaml/app-job.yaml) |
| app-multicontainer.yaml     | Set Up Multi-container Pods        | YAML to define a pod that runs more than one container                  | [app-multicontainer.yaml](yaml/app-multicontainer.yaml) |
| app-resources.yaml          | Configure Resource Usage           | YAML to configure resource requests and limits for your application     | [app-resources.yaml](yaml/app-resources.yaml) |
| app-secret-env.yaml         | Set Up Secrets as Env Variables    | YAML to define environment variables using secrets                      | [app-secret-env.yaml](yaml/app-secret-env.yaml) |
