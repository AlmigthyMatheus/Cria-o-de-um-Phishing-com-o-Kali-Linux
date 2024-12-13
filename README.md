# 🚨 **Criação de Phishing com o Kali Linux e SEToolkit** 🚨

Bem-vindo ao repositório de **Phishing com SEToolkit**! 🎯 Neste repositório, mostramos como criar um ataque de phishing utilizando o **SEToolkit** no **Kali Linux** e **Arch Linux**. O SEToolkit é uma ferramenta poderosa de engenharia social que pode ser usada para testar vulnerabilidades de segurança.

## 🔧 **Requisitos** 

- **Kali Linux** ou **Arch Linux** 🐧
- **Python 3.x** (instalado)
- Conhecimento básico em **Segurança Cibernética** 🛡️

## 📥 **Instalação do SEToolkit**

### 🐧 **Kali Linux**

No Kali Linux, o SEToolkit já vem pré-instalado. Caso não esteja instalado, basta executar:

```bash
sudo apt update
sudo apt install set

🖥️ Arch Linux

No Arch Linux, o SEToolkit pode ser instalado a partir do AUR (Arch User Repository). Use o seguinte comando para instalar:

yay -S setoolkit

Se você não tiver o yay, instale-o ou use o método de compilação manual para instalar o SEToolkit.
🚀 Iniciando o SEToolkit

Para iniciar o SEToolkit, use o comando:

sudo setoolkit

Este comando abrirá o menu principal do SEToolkit, onde você pode escolher várias opções para ataques de engenharia social.
🌐 Criando um Ataque de Phishing

    Selecione Social-Engineering Attacks.
    Em seguida, escolha Website Attack Vectors.
    Agora, selecione Credential Harvester Attack Method — este método captura credenciais enviadas a um site falso.
    Configure o URL do site de phishing que deseja simular.
    O SEToolkit criará automaticamente uma cópia do site e começará a capturar as credenciais enviadas.

⚠️ Como Resolver o Erro Comum: AttributeError: module 'cgi' has no attribute 'escape'

Esse erro ocorre nas versões mais recentes do Python (3.2+), pois o método cgi.escape() foi removido. Vamos corrigir isso! 💡
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

Agora, execute o SEToolkit novamente para ver se o erro foi corrigido:

    sudo setoolkit

🖼️ Imagens

Aqui estão algumas imagens ilustrativas para ajudá-lo a visualizar o processo:

    Tela de Login do SEToolkit:
    📸

    Terminal mostrando o envio de email e senha:
    📸

✅ Conclusão

Agora você sabe como criar um ataque de phishing utilizando o SEToolkit no Kali Linux e no Arch Linux! 🎉 Se você encontrou o erro relacionado ao cgi.escape(), agora sabe como corrigi-lo. 🙌

⚠️ Atenção: Use essas ferramentas somente para fins educacionais e de teste em ambientes controlados! O phishing é ilegal se realizado sem a permissão de quem está sendo atacado.

🌟 Divirta-se explorando o SEToolkit e aprenda mais sobre segurança cibernética! 🌟
