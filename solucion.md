## Tarefa 1.6. 1.6 logs + utilidade rndc + nsupdate

1. Fai que no equipo darthvader se faga un log de todas as consultas (/var/log/bind/queries.log) e de todas as actualizacions (/var/log/bind/update.log) a dous ficheiros de log diferentes. Captura a configuración. Amosa as capturas dos dous ficheiros de log, despois de facer consultas e actualizacións e transferencias de zona.

    - Modificación do ficheiro named.conf.local

        ![imaxe1](imaxes/solapt1.1.png)

    - Cambiar o usuario propietario do ficheiro /var/log/named/query.log:

        ![imaxe2](imaxes/solapt1.2.png)

    - Realizamos varias consultas:

        ![imaxe3](imaxes/solapt1.3.png)

    - Comprobamos os ficheiros de log:

        - /var/log/bind/queries.log:

            ![imxe4](imaxes/solapt1.4.png)

2. Investiga como co comando "dig" podes pedir unha copia dunha zona.

    - Transferencia de zona usando dig

        ![imaxe5](imaxes/solapt2.1.png)

3. Permite que o equipo darthvader poida ser controlado coa utilidade rndc desde un cliente ubuntu ou debian. Fai unha captura do servidor reiniciandose.

    - Creación da clave TSIG

        ![imaxe6](imaxes/solapt3.1.png)

    - Verificamos o contido do arquivo

        ![imaxe7](imaxes/solapt3.2.png)

    - Modificación ficheiro named.conf.options

        ![imaxe8](imaxes/solapt3.3.png)

    - Creación do ficheiro rndc.conf no cliente

        ![imaxe9](imaxes/solapt3.4.png)

    - Reiniciamos servizo e acedemos dende cliente

4. Instala unha zona dinámica no servidor darthvader chamada galaxia.lan e introduce os rexistros aaylasecura (192.168.20.239) e yarua (192.168.20.238). Esta zona debe ser cargada mediante rndc, e o servidor reiniciado con rndc. Proba tamén a eliminala con rndc. Inclue capturas do resultado dos comandos, comprobando tamén que se poden facer consultas.

    - rndc.conf do cliente:

        ![imaxe10](imaxes/solapt4.1.png)

    - rndc.key do servidor:

        ![imaxe11](imaxes/solapt4.2.png)

    - Definimos a zona galaxia.lan no named.conf.local do servidor

        ![imaxe12](imaxes/solapt4.3.png)

    - Creamos a zona db.galaxia.lan

        ![imaxe13](imaxes/solapt4.4.png)
    
    - Comprobamos que se engadiron os rexistros

        ![imaxe14](imaxes/solapt4.5.png)
    
5. Mediante a utilidade nsupdate, engade un rexistro chamado darthmaul (192.168.20.144) á zona starwars.lan empregando chaves

    - Engadimos o rexistro empregando nsupdate

        ![imaxe15](imaxes/solapt5.1.png)

    - Comprobamos a existencia do rexistro na zona

        ![imaxe16](imaxes/solapt5.2.png)