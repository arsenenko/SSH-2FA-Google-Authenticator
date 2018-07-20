# SSH-2FA-Google-Authenticator
<a href="https://ibb.co/e6RSWy"><img src="https://preview.ibb.co/dTsedd/two_factor_authentication_for_joomla_security_blog_banner_v4.jpg" alt="two_factor_authentication_for_joomla_security_blog_banner_v4" border="0"></a>

Хотите защитить свой SSH-сервер простой в использовании двухфакторной аутентификацией?
Google предоставляет необходимое программное обеспечение для интеграции системы одноразового пароля Google Authenticator (TOTP) с вашим SSH-сервером. При подключении вам нужно будет ввести код со своего телефона.

Google Authenticator (API)

Организация для пользователя root 
Все остальные по ключу или по паролю .

# Установка Ubuntu 16.04

root@arsenenko/home/aa# apt-get update -y

root@arsenenko/home/aa# apt-get install libpam-google-authenticator -y

# Запуск

root@arsenenko/home/aa# google-authenticator
     
Ответить на ряд вопросов :
Вы хотите, чтобы токены аутентификации были основаны на времени    
(y / n) y
Вы хотите, чтобы я обновил файл «~ / .google_authenticator» (y / n) y
Вы хотите запретить несколько использования одной и той же проверки подлинности
фишка? Это ограничивает вас одним логином примерно каждые 30 лет, но оно увеличивается
ваши шансы заметить или даже предотвратить нападения «человек-в-середине» (y / n) y
По умолчанию токены хороши в течение 30 секунд и для компенсации
возможный временной перекос между клиентом и сервером, мы разрешаем дополнительный
токен до и после текущего времени. Если у вас возникли проблемы с бедными
синхронизация времени, вы можете увеличить окно по умолчанию
от 1: 30 мин до 4 мин. Вы хотите сделать это (y / n) n
Если компьютер, в который вы входите, не затвердевает от грубой силы
попытки входа в систему, вы можете включить ограничение скорости для модуля аутентификации.
По умолчанию это ограничивает атакующих не более 3 попыток входа в систему каждые 30 секунд.
Вы хотите включить ограничение скорости (y / n) y







<a href="https://ibb.co/db5kjJ"><img src="https://preview.ibb.co/dV5UBy/000.png" alt="000" border="0"></a>

Необходимо установить предложения и отсканировать код " Google Authenticator " 














# Настройка SSH

2 Настройка конфигурации ssh

Вариант 1

root@arsenenko/home/aa# vim /etc/pam.d/sshd
@include common-auth   
auth required pam_google_authenticator.so <<<-- Эта строчка в конец конфига 

root@arsenenko/home/aa#  vim /etc/ssh/sshd_config
ChallengeResponseAuthentication yes
root@arsenenko/home/aa#  systemctl restart ssh



# Пример 

Вариант 1

root@arsenenko/home/aa# ssh root@arsenenko

 password: kjfdhykf)s^%^

 Verification code: 23146


<a href="https://imgbb.com/"><img src="https://image.ibb.co/fKGuTd/google_authenticator.jpg" alt="google_authenticator" border="0"></a><br /><a target='_blank' href='https://poetandpoem.com/William-Edmondstoune-Aytoun'>William Edmondstoune Aytoun</a><br />



