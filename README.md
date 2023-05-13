
### 1-configurar_hadoop
1. Crear red en docker
```code
docker network create --driver=bridge hadoop
```
2. Crear contenedores master and slave
```code
sh start-container.sh
```
3. El script anterior te deja dentro del contenedor hadoop-master, donde vas a ir a la carpeta config (esta carpeta ya la trae la imagen docker por defecto) y ejecutas **start-hadoop.sh** para iniciar el servicio de hadoop (levanta hdfs y yarn) :
```code
sh start-hadoop.sh
```
4. Estando dentro del contenedor hadoop-master creamos un archivo y lo movemos a hadoop:
```code
echo "texto para hadoop" > ejemplo.txt
hdfs dfs -mkdir -p platzi #Crear carpeta
hdfs dfs -ls #Listar carpeta creada
hdfs dfs -put ejemplo.txt platzi/ #Movemos el archivo
hdfs dfs -ls platzi/ #Ver nuestro archivo de texto dentro de la carpeta
```
5. Ir al navegador a ver el archivo de texto `` http://localhost:40070`` > Utilities > Browse from file system > user/root/platzi. Podremos ver nuestro archivo y los nodos en los que se encuentra disponible.

