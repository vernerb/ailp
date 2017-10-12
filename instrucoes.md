Instalando o atom - editor de textos do Github poderoso

sudo add-apt-repository ppa:webupd8team/atom -y && sudo apt-get update && sudo apt-get install atom -y

Criando um ambiente virtual para instalarmos as bibliotecas necessárias

$ virtualenv -p python3 penny

Este comando irá criar um esqueleto para podermos instalar as bibliotecas. Nosso primeiro teste será
o chatbot penny, já que não será muito inteligente. Cada nova versão com melhorias, iremos nomear com
um personagem de Big Bang Theory.

Para ativar o ambiente, deverá ser dado o comando:

cd penny

source bin/activate

após ser dado este comando, teremos um prompt parecido com:

(penny) userb@computer:~/projects/python3/ailp/penny/bin$

O (penny) entre parenteses significa que estamos com o nosso ambiente virtual ativado, e desta forma
poderemos incluir bibliotecas somente para o projeto, sem afetar a instalação padrão do Python no SO,
sendo que isto é altamente recomendável em ambinetes Linux que utilizam Python para suas funções internas.

Instalando o Chatterbot

Para instalar o Chatterbot, com o ambiente virtual ativo, daremos o seguinte comando:

$ pip install Chatterbot

Após concluída a instalação, iremos digitar um programa para testarmos um simples chatbot:

Crie o arqivo teste.py usando:

atom teste.py

Digite as linhas abaixo entre os tracejados:

---------------------------------------------------
from chatterbot import ChatBot

chatbot = ChatBot(
    'Teste',
    input_adapter='chatterbot.input.TerminalAdapter',
    output_adapter='chatterbot.output.TerminalAdapter',
    trainer='chatterbot.trainers.ListTrainer'
)

chatbot.train([
    "Oi",
    "Ola",
    "Boa tarde",
    "Boa tarde, tudo bem?",
    "Boa noite",
    "Boa noite, tudo bem?",
    "Bom dia",
    "Bom dia, tudo bem?"
    "Eu vou bem, e voce?",
    "Eu tambem!",
    "Quem e voce?",
    "Sou um chatbot",
    "Voce e burro",
    "Sou tao esperto quanto me programaram para ser",
    "Teste",
    "Por que voce digitou teste?"
])

print("Digite algo para iniciar o dialogo em ingles:")

while True:
    try:
        chatbot.get_response(None)
    except(KeyboardInterrupt, EOFError, SystemExit):
        print("*** Fim do programa")
        break
exit(0)
---------------------------------------------------

salve o arquivo e digite python3 teste.py

Caso ocorram erros, corrija os erros de digitação. Digite Bom dia ou frases que você colocou no traninning list.

Coisas novas serão acrescentadas durante a conversa, mas não espere bons resultados.

Concluindo estas instruções, poderemos iniciar nossos trabalhos. Recomendo que leiam a documentação no site:

http://chatterbot.readthedocs.io/en/stable/setup.html

Boa diversão!
