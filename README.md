# POCDotNetCoreRabbitMQ
Send a message from a dot net core MVC app to Worker service to process through Rabbit MQ all deployed on docker containers.</br>
</br>Pre-requisites:
</br> Install Docker Windows
</br>Step 1: Install Rabbit MQ container
</br> for RabbitMQ 3.9, the latest series
</br>docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.9-management
</br>Step 2: Run the POCWindows Worker service 2 and run its image in docker windows.
</br>Step 3: Run the PushMessage MVC to push message from this app and recieve in worker service.
