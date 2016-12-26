


# Permissão de arquivo com SElinux

O SELinux é uma importante camada de proteção para os servidores Linux. Infelizmente, 
é muito comum – e até corriqueiro – os administradores de servidores desabilitarem ele, sem 
saber o quão importante ele é para a segurança do sistema.


# Problema

O comando chmod não funciona para dar permissão aos arquivos porque o SElinux está ativado.



# Solução

Executar o comando:

´chcon -t httpd_sys_content_t -R logfiles´


Saiba mais:

* http://gesielbernardes.eti.br/configurar-selinux.html
* https://forums.phpfreaks.com/topic/66920-is-writable-returns-false-no-matter-whatwhere/
* http://stackoverflow.com/questions/29343809/php-is-writable-function-always-returns-false-for-a-writable-directory




