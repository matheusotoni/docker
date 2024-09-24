# Usando a imagem do RabbitMQ versão 4.0.1-management
FROM rabbitmq:4.0.1-management

LABEL RabbitMQ.Version="4.0.1-management"

# Habilitar os plugins necessários
RUN rabbitmq-plugins enable --offline rabbitmq_management_agent rabbitmq_prometheus rabbitmq_shovel rabbitmq_shovel_management

# Definir variáveis de ambiente para login e senha
ENV RABBITMQ_DEFAULT_USER=guest 
ENV RABBITMQ_DEFAULT_PASS=guest

# Expôr as portas
# 5672: Porta padrão de comunicação AMQP
# 15672: Porta de gerenciamento (management plugin)
# 8081: Porta de gerenciamento (management plugin)
EXPOSE 5672 15672 8081

# Comando para iniciar o RabbitMQ
# CMD ["rabbitmq-server"]