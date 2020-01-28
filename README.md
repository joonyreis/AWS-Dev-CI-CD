# AWS-Dev-CI-CD
Projeto de teste de integração com aws para entregas continuas e deploy 

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/Bit%20Codebuild%20S3.png)


**1.**	Acesse o **CodeBuild da AWS**, disponível em **Serviços -> Ferramentas do Desenvolvedor -> CodeBuild**;

**2.**	Navegue até o menu **Compilação -> Projetos de Compilação**;

**3.**	Clique sobre o botão de **Criar projeto de Compilação**;


![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img1.png)


**4.**	Insira os dados solicitados para seu projeto;

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img2.png)


**5.**	Selecione a origem do fonte, podendo ser escolhida dentre as várias opções de integração existentes com AWS CodeBuild

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img3.png)


**6.**	Ambiente para execução dos passos (instalações, build, testes, arquivos) 

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img4.png)


**7.**	Comandos do Buildspec, são passos e validações que serão seguidas na execução. Dica: Utilize a opção "Usar um arquivo buildspec"

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img5.png)


**8.**	Artefatos são arquivos gerados através dos eventos realizados nos passos configurados no buildspec. Estes arquivos podem ser armazenados em um S3 para análise posterior ou comparativos

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img6.png)


**9.**	Logs da máquina que realizou os passos do buildspec

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img7.png)


**10.**	Criar projeto de compilação 

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img61.png)


**11.**	Após a criação, ele irá exibir na lista de projetos de compilação.


**3.2.2 Configurando Buildspec**  


O repositório utilizado de exemplo é público e disponível para visualização em https://github.com/joonyreis/AWS-Dev-CI-CD e o projeto criado de compilação na região ca-central-1 (Canadá Central) com a conta AWS pessoal foi **cicdAngularTest**.

O arquivo buildspec.yml será descrito e comentado abaixo

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img8.png)



**3.2.3 Configurando regras de acesso**


Vamos acessar o menu **Serviços - > Segurança, Identidade e Conformidade -> IAM -> Gerenciamento de acesso -> Funções**
 
Selecione a função respectiva com o nome do projeto criado no codeBuild e atribua as regras de acesso de acordo com o projeto.


**Permissões necessárias para uso da integração segue na lista abaixo:**


●  	AmazonS3FullAccess


●  	AWSCodeBuildDeveloperAccess


●  	AWSCodeBuildAdminAccess
 
 
 
**3.2.4 Configurando eventos para execução automática do codeBuild**

        	
Clique sobre o projeto e logo após no botão **Editar -> Origem -> Role** o mouse até **Eventos de webhook**.

Podem ser criados filtros e condições para execução de acordo com os eventos gerados (push e pull), assim como condicionais exibidas abaixo .

![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img9.png)



**3.2.5 Status e histórico de builds**   	

 
Ao clicar sobre o projeto de build exibirá todo o histórico de operações, contendo informações macro e informações mais detalhadas clicando sobre a execução. 


![Alt Text](https://github.com/joonyreis/AWS-Dev-CI-CD/blob/master/img10.png)

