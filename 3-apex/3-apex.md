# Oracle APEX

## 📌 Introdução

>**O Oracle APEX (Application Express) é uma plataforma de desenvolvimento low-code que permite a criação rápida e fácil de aplicações seguras, escaláveis e altamente responsivas diretamente no Oracle Database, sem a necessidade de infraestrutura complexa.** 

![APEX](images/apex.png)

### ➡️ **Como o Oracle APEX revoluciona o desenvolvimento de aplicações no Oracle Database?**

> Com o Oracle APEX, desenvolvedores podem criar aplicações empresariais modernas por meio de uma interface intuitiva que combina design visual, componentes integrados e funcionalidades avançadas, como gráficos interativos, relatórios dinâmicos e dashboards. O APEX aproveita as capacidades nativas do Oracle Database, como segurança, alta disponibilidade e desempenho, permitindo a criação de workspaces, o upload de aplicações e a integração com serviços externos via credenciais e APIs. Com poucos cliques, é possível importar arquivos SQL, configurar parâmetros de segurança e realizar customizações rápidas e eficientes.


<br>


### 📌 **Objetivos**

  Guiar os participantes na criação e configuração de um ambiente APEX no Oracle Cloud Infrastructure (OCI) para implementar uma aplicação baseada em IA generativa.  

O que você aprenderá:

  - Criar um workspace no APEX.  
  - Importar e instalar uma aplicação.  
  - Ajustar credenciais para integração com serviços do OCI.  
  - Realizar de testes práticos para validar a aplicação.  

<br>
### **Recursos e Suporte**:

- **Documentação da Oracle Cloud**: [Getting started with vectors in 23ai](https://blogs.oracle.com/coretec/post/getting-started-with-vectors-in-23ai)
- **Tutoriais**: [Oracle Database 23ai - Oracle AI Vector Search & Retrieval Augmented Generation (RAG) with Oracle APEX](https://www.linkedin.com/pulse/oracle-database-23ai-ai-vector-search-retrieval-augmented-rao-bqkcf/)


### _**Aproveite sua experiência na Oracle Cloud!**_


## Task 1:	Criação de Workspace e Import de aplicação em ambiente APEX

Faça o login no Oracle Cloud Infrastructure (OCI) e valide se a região de Chicago se encontra disponível para uso.

   ![Validate Region](images/validate-region.png " ")

> **Caso a região de Chicago não esteja disponível, clique em manage region (caso já esteja disponível pule para a sessão 2 - Criação de Autonomous Database)** 
![Manage Region](images/manage-region.png)

Busque por **US Midwest (Chicago)** e clique no botão subscribe. O processo de subscrição pode levar alguns minutos, aguarde para dar sequência ao workshop. Clique no ícone escrito **Oracle Cloud** no canto esquerdo e faça logoff e login para validar se a região já foi subscrita.

![Subscribe Region](images/subscribe-region.png)

## Task 2: Criação de Autonomous Database

Clique no menu de hambúrger do canto superior esquerdo da tela, na sequência navegue até a página de gestão de autonomous databases.

![Autonomous Acess](images/autonomous-acess.png)

Na página de gestão de Autonomous Databases, clique em create autonomous database. Selecione **ATP ou ADW**
  
![Create Autonomous](images/create-autonomous.png)

Escolha a versão 23ai para o banco de dados:

![Create 23AI](images/create-23ai.png)

Coloque uma senha que consiga lembrar, escolha **secure access from everywhere** e clique em **Create Autonomous Database**:

![Secure Acess](images/secure-acess.png)

Aguarde até a conclusão da criação: 
- Ícone amarelo = criando; 
- Ícone verde = pronto para uso;
![Yellow ADW](images/yellow-adw.png)
![Green ADW](images/green-adw.png)

## Task 3: Configurando o Autonomous Database

Clique no ícone chamado database actions e SQL:
![Database Actions](images/database-actions.png)

Caso seja requisitado, o usuário é **admin** e a senha é a **fornecida na criação do autonomous database da etapa anteiror.**
Feche todos os tutoriais que aparecerão na página.
Copie, cole e execute os comandos abaixo:


    <copy>  
        --Criação de credencial
    BEGIN
        DBMS_CLOUD.CREATE_CREDENTIAL(
            credential_name => 'OBJ_STORE_CRED',
            username => 'oracleidentitycloudservice/CAIO.OLIVEIRA@ORACLE.COM',
            password => 'teste'
        );
    END;
    /

    --Download de Modelo onnx do object storage para diretorio autonomous
    begin
    dbms_cloud.get_object(
        credential_name => 'OBJ_STORE_CRED'
        , object_uri => 'https://objectstorage.sa-saopaulo-1.oraclecloud.com/p/nS9blF5U2ETiZT7YKZ_zrXtPOEH2Xf22TbdlpK99xZIEPmZedx4_eFBX4khYykmw/n/idi1o0a010nx/b/TDC/o/intfloatmodelsmall.onnx'
        , directory_name => 'DATA_PUMP_DIR'
        , file_name => 'intfloatmodelsmall.onnx'
    );
    end;
    /

    --Criação de usuário/schema para import do modelo e criação da aplicação
    create user demo identified by "WORKSHOPsec2019##";
    grant dwrole to demo;
    grant unlimited tablespace to demo;
    grant read, write on directory data_pump_dir to demo;

    --Import de modelo onnx para autonomous
    EXECUTE dbms_vector.load_onnx_model('DATA_PUMP_DIR', 'intfloatmodelsmall.onnx', 'demo.doc_model', JSON('{"function" : "embedding", "embeddingOutput" : "embedding" , "input": {"input": ["DATA"]}}'));
    commit;

    </copy>

Execute conforme indicado abaixo:

![Execute Code](images\execute-code.png)


## Agradecimentos

- **Autores** - Caio Oliveira
- **Autor Contribuinte** - Isabelle Anjos
- **Última Atualização Por/Data** - Janeiro 2025

## Declaração de Porto Seguro (Safe Harbor)

O texto a seguir tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 
