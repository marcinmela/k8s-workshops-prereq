# Wymagania dla systemu Linux

## Git

W trakcie warsztatów wymagane będzie pobranie zawartości repozytorium Git. Należy zainstalować klienta Git z [instrukcji](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)

## Kubernetes

Lokalny klaster Kubernetes można zainstalować na potrzeby warsztatów, przy użyciu Minikube. Wymagane jest do tego wsparcie wirtualizacji - należy włączyć w BIOSie.

### Minikube

Przed zainstalowaniem Minikube należy zainstalować [VirtualBox](https://www.virtualbox.org/wiki/Downloads). 
W przypadku problemów z instalacją VirtualBoxa warto sprawdzić `Preferencje systemowe` \ `Ochrona i prywatność` i tam zaznaczyć *"Dopuszczaj aplikacje pobrane z AppStore i od zidentyfikowanych developerów"* oraz zweryfikować czy VirtualBox nie został wpisany na listę zablokowanych aplikacji. Więcej porad na problemy z instalacją VirtualBoxa można znaleźć [tutaj](https://medium.com/@DMeechan/fixing-the-installation-failed-virtualbox-error-on-mac-high-sierra-7c421362b5b5)

Następny krok to instalacja [narzędzia `kubectl`](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-macos) oraz [Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/).

### Weryfikacja instalacji lokalnego klastra Kubernetes

Aby uruchomić lokalny klaster Kubernetes należy w wierszu poleceń wykonać polecenie `minikube start --vm-driver virtualbox` jak poniżej.

```console
$ minikube start --vm-driver virtualbox
😄  minikube v1.5.2 on Darwin 10.14.1
💡  Tip: Use 'minikube start -p <name>' to create a new cluster, or 'minikube delete' to delete this one.
🏃  Using the running virtualbox "minikube" VM ...
⌛  Waiting for the host to be provisioned ...
🐳  Preparing Kubernetes v1.16.2 on Docker '18.09.9' ...
🔄  Relaunching Kubernetes using kubeadm ... 
⌛  Waiting for: apiserver
🏄  Done! kubectl is now configured to use "minikube"
```

Następnie trzeba uruchomić komendę `kubectl version`. Oto przykładowy wynik uruchomienia wspomnianej komendy na poprawnie zainstalowanym klastrze:

```console
$ kubectl version
Client Version: version.Info{Major:"1", Minor:"16", GitVersion:"v1.16.0", GitCommit:"2bd9643cee5b3b3a5ecbd3af49d09018f0773c77", GitTreeState:"clean", BuildDate:"2019-09-18T14:36:53Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"darwin/amd64"}
Server Version: version.Info{Major:"1", Minor:"16", GitVersion:"v1.16.2", GitCommit:"c97fe5036ef3df2967d086711e6c0c405941e14b", GitTreeState:"clean", BuildDate:"2019-10-15T19:09:08Z", GoVersion:"go1.12.10", Compiler:"gc", Platform:"linux/amd64"}
```

Wynik uruchomienia polecenia może być różny w zależności od daty jej wykonania - wystarczy upewnić się, że polecenie poprawnie zwróciło wersje klienta oraz serwera. Jeżeli weryfikacja przebiegła poprawnie można zakończyć działanie lokalnego klastra poleceniem `minikube stop`.

```console
$ minikube stop
✋  Stopping "minikube" in virtualbox ...
🛑  "minikube" stopped.
```

## IDE

Sugerowanym edytorem podczas warsztatów jest [Visual Studio Code](https://code.visualstudio.com/) z aktywowanym rozszerzeniem [Kubernetes](https://code.visualstudio.com/docs/azure/kubernetes#_install-the-kubernetes-extension).
