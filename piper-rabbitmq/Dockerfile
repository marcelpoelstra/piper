FROM rabbitmq:3.7.28-management

COPY rabbitmq_delayed_message_exchange-0.0.1.ez /plugins/rabbitmq_delayed_message_exchange-0.0.1.ez

RUN rabbitmq-plugins enable --offline rabbitmq_delayed_message_exchange
