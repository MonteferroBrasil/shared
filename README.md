# Instalação do Docker e Kubernetes no Hyper-V

Este guia explica como configurar Docker e Kubernetes no Hyper-V, criando um ambiente de desenvolvimento para suas aplicações Java Web com Spring Boot e MySQL.

## 1. Docker no Hyper-V

Docker pode ser executado no Windows utilizando o Hyper-V como backend de virtualização. Siga os passos abaixo para habilitar o Hyper-V e instalar o Docker Desktop.

### Passos para Instalar o Docker no Hyper-V

1. **Habilitar o Hyper-V**:
   - Abra o **Painel de Controle** → **Programas** → **Ativar ou desativar recursos do Windows**.
   - Marque a opção **Hyper-V** e clique em **OK**.
   - Reinicie o computador para aplicar as alterações.

2. **Instalar o Docker Desktop**:
   - Baixe o [Docker Desktop para Windows](https://www.docker.com/products/docker-desktop/).
   - Durante a instalação, o Docker detectará o Hyper-V e o utilizará como backend.
   - Após a instalação, o Docker será executado como uma máquina virtual gerenciada pelo Hyper-V.

3. **Configurar o Docker**:
   - Abra o Docker Desktop e faça as configurações necessárias, como a alocação de CPU e memória para os contêineres.
   - Agora você já poderá criar contêineres usando o Docker no Hyper-V.

## 2. Kubernetes no Hyper-V

Para configurar um cluster Kubernetes local no Hyper-V, você pode usar o **Minikube**, uma ferramenta que facilita a criação de clusters Kubernetes em ambientes locais. Minikube suporta o Hyper-V como uma das opções de virtualização.

### Passos para Instalar o Minikube no Hyper-V

1. **Instalar o Minikube**:
   - Baixe o [Minikube](https://minikube.sigs.k8s.io/docs/start/) e siga as instruções de instalação para Windows.

2. **Configurar o Hyper-V como Driver de Virtualização**:
   - Abra o PowerShell ou o Prompt de Comando como administrador e execute o comando:
     ```bash
     minikube config set driver hyperv
     ```
   - Isso configura o Hyper-V como o driver de virtualização para o Minikube.

3. **Iniciar o Minikube**:
   - Com o driver configurado, inicie o cluster Minikube executando:
     ```bash
     minikube start --memory=4096 --cpus=2
     ```
   - Ajuste os valores de CPU e memória conforme necessário para o seu ambiente.

4. **Testar o Kubernetes**:
   - Após iniciar o Minikube, você poderá gerenciar o cluster Kubernetes usando o comando `kubectl`, o cliente de linha de comando do Kubernetes.
   - O Minikube cria um ambiente Kubernetes local que é ideal para desenvolvimento e testes.

## Observações

- **Recursos do Servidor**: Hyper-V e Kubernetes consomem CPU e memória. Alocar recursos adequados é importante para evitar lentidão.
- **Produção**: Esta configuração é ideal para testes e desenvolvimento. Para produção, recomenda-se o uso de servidores dedicados ou uma solução de Kubernetes na nuvem para melhor escalabilidade e gerenciamento.

Com essas instruções, você poderá criar um ambiente Kubernetes e Docker no Hyper-V para gerenciar suas aplicações Java Spring Boot e MySQL localmente.
