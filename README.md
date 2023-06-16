# Explicação da implementação

O código consiste em dois arquivos principais: um publisher e um subscriber. O publisher captura frames em um intervalo, definido por mim, de um arquivo de vídeo e os publica em um tópico. O subscriber recebe os quadros publicados nesse tópico, converte-os em formato adequado e os salva localmente. Por fim, na rota "/images" realiza o upload das imagens para o Supabase. O Supabase é uma plataforma que permite armazenar e gerenciar arquivos de forma eficiente.

O publisher usa a biblioteca rclpy para se comunicar com o ROS 2, enquanto o subscriber recebe os frames do tópico usando a mesma biblioteca. A conversão dos quadros é feita com o auxílio da biblioteca CvBridge, que converte entre os formatos de imagem do ROS 2 e do OpenCV.

O servidor salva os quadros em uma pasta local chamada "recebidos" e, em seguida, realiza o upload desses quadros para o Supabase usando a biblioteca Supabase Python. O Supabase é configurado com uma URL e uma chave de acesso, permitindo o envio dos quadros para um bucket específico chamado "arquivos".

#Vídeo da implementação
