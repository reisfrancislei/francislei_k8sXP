# Francislei - Curso de K8s

1 - Exportar o diretorio /k8s via nfs

- <b>Pré requisito</b> - Instalar <i><b>nfs-kernel-server</b></i> com o comando abaixo:
```sh
apt-get install -y nfs-kernel-server
````
- Criar o diretório <i><b>/opt/k8s</b></i>
```sh
mkdir /opt/k8s
```
- Dar as devidas permissões
```sh
chmod 1777 /opt/k8s
```
- É necessário definir quais diretórios serão exportos via NFS, fazemos isso incluindo o conteúdo abaixo no arquivo <i><b>/etc/exports</b></i>
```sh
echo "/opt/k8s *(rw,sync,no_root_squash,subtree_check)" >> /etc/exports
```
- Após isso executar:
```sh
exportfs -ar
```

2 - Criar index personalizado 
```sh
echo "Curso kubernetes - Codeops" >> /opt/k8s/index.html
```
3 - Criar <i><b>PV</b></i>
```sh
kubectl create -f pv.yaml
```

4 - Criar <i><b>PVC</b></i>
```sh
kubectl create -f pvc.yaml
```

5 - Criar <i><b>Deployment</b></i>
```sh
kubectl create -f deployment.yaml
```

6 - Criar <i><b>Service</b></i>
```sh
kubectl create -f service.yaml
```
