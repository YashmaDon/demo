# demo
Test 4/5
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