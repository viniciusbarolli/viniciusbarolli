- 👋 Hi, I’m @viniciusbarolli
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
viniciusbarolli/viniciusbarolli is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
from telegram import Bot
import schedule
import time

# Insira seu token de API do Telegram aqui
TOKEN = 'seu_token_aqui'

# Criação do objeto bot
bot = Bot(token=TOKEN)

# ID do chat ou do usuário para onde a mensagem será enviada
chat_id = 'chat_id_aqui'

# Função para enviar a mensagem
def enviar_mensagem():
    message_text = 'Olá, esta é uma mensagem agendada!'
    bot.send_message(chat_id=chat_id, text=message_text)

# Agendamento da tarefa para um horário específico
schedule.every().day.at('09:00').do(enviar_mensagem)  # Exemplo: 09:00

# Loop principal para executar o programador de horários
while True:
    schedule.run_pending()
    time.sleep(1)
