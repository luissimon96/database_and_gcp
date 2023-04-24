# database_and_gcp

Neste Tutorial vamos criar um banco de dados utilizando o GCP.

Primeiro precisamos acessar o menu laterado do console e escolher a opção "SQL"
Clicar no botão "Criar Instância" e depois escolher qual banco de dados desejamos criar:
![image](https://user-images.githubusercontent.com/55896446/233873151-8ba7aecc-045f-4861-b6d6-e971e8311996.png)

Estarei criando uma instancia do MySQL.
Chegando na tela: Criar uma instância do MySQL, precisamos informar alguns parâmetros como:
Id da Instância, Senha, Versão desejada e a região que desejamos provisionar esse recurso.
Como esse é um tutorial não estarei deixando o banco produtivo e sim na configuração de Desenvolvimento, podemos seguir clicando no botão "Criar instância"
Lembrando de que em Redes podemos definir o IP para Particular se assim for mas também adicionar a mesma rede do cluster Kubernetes para que possamos realizar a conexão com o Adminer posteriormente
![image](https://user-images.githubusercontent.com/55896446/233873442-74662ec0-3ecf-4105-9125-76172cd0fe79.png)
Isso irá criar toda a infra básica para comportar o serviço de banco de dados;

Podemos seguir com a conxão assim que finalizar, esse processo de criação deve demora de 5 a 10 minutos:

Acessar o Kubernetes e aplicar o adminer.yaml,
para aplicar devemos rodar o seguinte comando:
```
kubectl apply -f adminer.yaml
```
para consultar o resultado devemos executar os seguintes comandos:
```
kubectl get deployment
kubectl get pods
kubectl get service
```
![image](https://user-images.githubusercontent.com/55896446/233893432-5a800470-fea6-4389-a450-1aab5b14f17c.png)

Assim que o mesmo obtiver o IP publico podemos seguir com a configuração da conexão:
![image](https://user-images.githubusercontent.com/55896446/233893118-6e2be13c-9c37-4f8d-ab95-cbf29959aed7.png)

Acessando o IP público da aplicação devemos preencher os dados do banco para que possamos autenticar e visualizar as tabelas do mesmo:
Tela do Adminer:
![image](https://user-images.githubusercontent.com/55896446/233893711-37278ef3-32ff-4a05-b732-0eb305461987.png)

IP privado do Banco:
![image](https://user-images.githubusercontent.com/55896446/233893733-592cb391-5e51-4ae2-ad71-c2927853bc8f.png)
Com este ip nas mãos já podemos começar a preencher os dados:
![image](https://user-images.githubusercontent.com/55896446/233893829-e643364c-2295-40f0-bc12-599655fb8fed.png)

Em usuário pode ser criado diretamente no campo usuários do SQL:
![image](https://user-images.githubusercontent.com/55896446/233893901-aa84a314-8b0d-4f83-be9f-c9cfeef17478.png)

Lembrando que na criação podemos exigir a obrigatoriedade do usuário tenha permissão ou não gerenciado pelo IAM:
![image](https://user-images.githubusercontent.com/55896446/233894056-d2aec97b-d491-4eb7-b9d4-bd8de3279b08.png)

Clicando em entrar já podemos ter acesso ao nosso banco de dados: ![image](https://user-images.githubusercontent.com/55896446/233894186-1fb8c580-5cc4-43c0-bdf4-a68fa5479646.png)
![image](https://user-images.githubusercontent.com/55896446/233894321-a659aad7-0566-4ca5-865a-c019223b1f79.png)


E lembrando, sempre que finalizar seus estudos ou laboratórios excluir toda a infra para que não continue cobrnado mesmo após os testes.
