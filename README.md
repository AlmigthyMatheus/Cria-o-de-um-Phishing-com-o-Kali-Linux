# 🚨 **Criação de Phishing com o Kali Linux e SEToolkit** 🚨

Bem-vindo ao repositório de **Criação de Phishing com SEToolkit**! 🎯 Neste guia, mostramos como criar um ataque de phishing utilizando o **SEToolkit** em **Kali Linux** e **Arch Linux**. O SEToolkit é uma poderosa ferramenta de engenharia social, usada para testar vulnerabilidades de segurança.

---

## 🔧 **Requisitos**

Antes de começar, certifique-se de ter o seguinte:

- **Kali Linux** ou **Arch Linux** 🐧
- **Python 3.x** (instalado) 🐍
- Conhecimento básico em **Segurança Cibernética** 🛡️

---

## 📥 **Instalação do SEToolkit**

### 🐧 **No Kali Linux**

O SEToolkit já vem pré-instalado no Kali Linux. Caso não esteja instalado, basta executar o seguinte comando:

```bash
sudo apt update
sudo apt install set
```

🖥️ No Arch Linux

No Arch Linux, você pode instalar o SEToolkit a partir do AUR (Arch User Repository). Use o seguinte comando:

yay -S setoolkit

Se você não tiver o yay, instale-o ou use o método de compilação manual para instalar o SEToolkit.
🚀 Iniciando o SEToolkit

    Para iniciar o SEToolkit, digite o seguinte comando no terminal:

sudo setoolkit

    Isso abrirá o menu principal do SEToolkit, onde você pode escolher várias opções para realizar ataques de engenharia social.

🌐 Criando um Ataque de Phishing

Siga as etapas abaixo para criar seu ataque de phishing:

    Selecione Social-Engineering Attacks.
    Escolha Website Attack Vectors.
    Selecione o Credential Harvester Attack Method – este método captura credenciais enviadas a um site falso.
    Configure o URL do site de phishing que você deseja simular.
    O SEToolkit criará automaticamente uma cópia do site e começará a capturar as credenciais enviadas.

⚠️ Como Resolver o Erro Comum: AttributeError: module 'cgi' has no attribute 'escape'

Esse erro ocorre devido à remoção do método cgi.escape() nas versões mais recentes do Python (3.2+). Vamos corrigir isso! 💡
🛠️ Solução para Kali Linux e Arch Linux

    Abra o arquivo harvester.py para edição:

sudo nano /usr/share/set/src/webattack/harvester/harvester.py

    Localize a linha que utiliza cgi.escape():

filewrite.write(cgi.escape("PARAM: " + line + "\n"))

    Substitua cgi.escape() por html.escape(), que é compatível com versões mais recentes do Python:

import html
filewrite.write(html.escape("PARAM: " + line + "\n"))

    Salve o arquivo. Se estiver usando o editor nano, pressione CTRL + O para salvar e depois CTRL + X para sair.

    Reinicie o SEToolkit:

sudo setoolkit

Isso deve corrigir o erro e permitir que o SEToolkit funcione corretamente.
🖼️ Imagens

Aqui estão algumas imagens ilustrativas para ajudá-lo a visualizar o processo:

    Tela de Login do SEToolkit:

    Terminal mostrando o envio de email e senha:

✅ Conclusão

Parabéns! Agora você sabe como criar um ataque de phishing utilizando o SEToolkit tanto no Kali Linux quanto no Arch Linux! 🎉

Se você encontrou o erro relacionado ao cgi.escape(), agora sabe como corrigi-lo. 🙌
