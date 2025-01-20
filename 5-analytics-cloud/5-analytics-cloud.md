# Oracle Analytics Cloud

## Introdução

>**Com o Oracle Analytics Cloud, se aprimora as análises dos seus dados com funcionalidade estatísticas e de IA com sugestões para criação de visualizações que podem enriquecer seu Painel Analítico.** 

Complementando a plataforma de Self-service Analytics, o OAC conta com um motor de Business Intelligence proveniente do OBIEE (solução extremamente estabelecida no mercado), que permite construção de Modelos Dimensionais, Hierarquias, e outras estruturas para otimizar o consumo dos dados, como Relatórios e Dashboards.

Toda a filosofia da solução gira ao redor dos conceitos de Augmented Analytics, tema muito recorrente em análises de companhias especializadas, como o Gartner. Ele se resume em enriquecer as análises com conceitos de Inteligência Artificial e Machine Learning, dando acesso a abordagens estatísticas avançadas para qualquer perfil de usuário, e não apenas aos que possuem vasto conhecimento sobre o tema. Nossa solução é classificada como **‘Líder’ no Quadrante Mágico do Gartner**, principal referência para avaliação e comparação de tecnologias hoje em dia.

<br>
### **Objetivos**

O objetivo deste workshop é demonstrar de forma prática como utilizar a ferramenta do Oracle Analytics Cloud e algumas funcionalidade de AI&ML embarcadas no OAC. Durante o workshop, você aprenderá a criar visualizações, adicinar estatísticas nas análises em um cenário que dados abertos da Marinha Brasileira (https://dados.gov.br/dados/conjuntos-dados/embarcacoes).

<br>
### **Recursos e Suporte**:

- **Documentação da Oracle Cloud**: [Getting started with Oracle Analytics Cloud](https://docs.oracle.com/en/cloud/paas/analytics-cloud/index.html)
- **Tutoriais**: [Oracle Analytics Cloud - Explore Funcionalidades com Tutoriais](https://docs.oracle.com/en/cloud/paas/analytics-cloud/tutorials.html)


### _**Aproveite sua experiência na Oracle Cloud!**_


## 1️⃣ Acessar OAC 

1. Clique no menu de hambúrger do canto superior esquerdo da tela, na sequência navegue até a página de gestão do Oracle Analytics Cloud.
   ![Analytics Cloud Acess](images/AcessoOAC.png)


2. Selecione a instância do OAC criada anteriormente. Agora abra o ambiente clique no botão **Analytics Homepage**.
   ![Analytics Cloud Homepage](images/AcessoOAC1.png)
   ![Analytics Cloud Homepage](images/AcessoOAC2.png)


<br>
3. Após o acesso da Homepage do OAC, faça o download do arquivo .dva com o material do laboratório: [Painel das Embarcações Brasileiras](https://objectstorage.us-ashburn-1.oraclecloud.com/n/idi1o0a010nx/b/Fast_Track/o/Lab%20Analytics%20-%20Embarca%C3%A7%C3%B5es%20Brasil.dva)

4. Em seguida, clique nos 3 pontos, ao lado do ícone do perfil. Selecione **Import Workbook**, escolha o arquivo .dva que acabou de baixar no passo anterior.
   ![Import do Arquivo](images/Import1.png)
   ![Import do Arquivo](images/Import2.png)
   ![Import do Arquivo](images/Import3.png)

5. Após a importação você terá acesso ao dataset (Conjunto de Dados) **Brasil-Embarcações** e ao workbook que vamos fazer, se quiser dar uma olhada como ele vai ficar no final só entrar nele **Lab Analytics - Embarcações Brasil**. 
   ![Homepage depois do import](images/Import4.png)


6. (OPCIONAL) Se quiser mudar o idioma da ferramenta, clique no Ícone do Perfil, selecione Perfil. Depois só escolher o Idioma e a Configuração Regional do OAC. 
   ![Perfil - Idioma](images/Perfil.png)
   ![Perfil - Idioma](images/Perfil2.png)


## 2️⃣ Criação do Dashboard - Visualizações

1. Na Homepage do OAC, selecione o conjunto de dados **Brasil-Embarcações**. Irá abrir o workbook (Pasta de Trabalho), uma tele em branco para montar o Painel com análises e visualizações. 
![Conjunto de Dados para montar Painel](images/Workbook1.png)
![Painel com Conjunto de Dados selecionado](images/Workbook2.png)

2. Na tela em branco do painel, selecione os dados da primeira coluna da esquerda, segurando o _CTRL+Clique_  **Quantidade, Latitude, Longitude**. Agora, arraste os itens selecionados para a Tela, e como sugestão o OAC já sugere que a visualização seja um Mapa.
![Visualização Mapa](images/Workbook3.png)
![Visualização Mapa](images/Workbook4.png)

4. Pode alterar a propriedade para personalizar o mapa. Na segunda coluna onde fica a gramática e a propriedade do gráfico, selecione o ícone superior de propriedades e vá até ícone de mapa na segunda linha. Pode alterar a propriedade do Mapa, em cada ícone da segunda linha tem acesso a um tipo de personalização da visualização. 
![Propriedades Visualização](images/Workbook5.png)

5. Pode deixar no modo que achar mais agradável, para continuar vou deixar no modo Dark/Escuro do Mapa.
![Propriedades Visualização](images/Workbook6.png)

6. Criar um gráfico de Barras. Seleciona o campos desejados na coluna da esquerda onde fica os dados, segurando o _CTRL+Clique_  **Estado e Quantidade**. Agora, arraste os itens selecionados para a Tela, ao lado do Mapa, aparece uma faixa verde na posição onde a visualização vai ficar. 
![Gráfico de Barra](images/Barra1.png)

7. Para ordenar os dados do gráfico selecione o ícone com uma seta para cima e outra para baixo, como mostrado na imagem. E então selecione a forma que deseja ordenar os dados. 
![Ordenar Dados](images/Ordenar1.png)
![Ordenar Dados](images/Ordenar2.png)
![Ordenar Dados](images/Ordenar3.png)

8. Salve seu trabalho até agora. Selecione o ícone do disquete no campo direito superior. Dê um nome para o seu Painel e salve. 
![Salvar Painel](images/Save.png)

## 3️⃣ Adição de Estatística nas Visualizações

1. Para adicionar estatísticas como: _Previsão, Linha de Tendência, Linha de Referência, Outliers ou Cluster_. 
<br> Seleciona a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolhe a opção **Outliers**, trará os pontos que destoam do grupo. 

   ![Estatística - Outliers](images/Outliers.png)
   ![Estatística - Outliers](images/Outliers2.png)

2. Para deixar uma visualização mais personalizada pode adicionar um filtro para trazer os _**10 maiores valores**_. 
<br> Selecione o dado **Quantidade** na primeira coluna e traga para segunda coluna, na gramática do painel para adionar **Quantidade** em **Filtros**. 
<br> Personalize o filtro, definindo _N Mais Altos_ e Contragem _10_. 

   ![Filtro na Visualização](images/Filtro.png)
   ![Filtro na Visualização](images/Filtro1.png)

3. Ao adicionar mais algumas métricas de estatística, como Linha de Referência. 
<br> Seleciona a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolhe a opção **Linha de Referência**. Deixe na Função Média. 

   ![Linha de Referência](images/Referencia1.png)
   ![Linha de Referência](images/Referencia2.png)

4. Repita o passo anterior. 
<br> Seleciona a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolhe a opção **Linha de Referência**. Deixe na Função Mediana, alterando a cor da linha para ficar diferente.   

   ![Linha de Referência](images/Referencia3.png)
   ![Linha de Referência](images/Referencia4.png)

<br>
### **OPCIONAL**

5. Criar uma visualização de Nuvem de Palavras e utilizá-la como filtro. 
Selecione os campos desejados **Embarcao e Quantidade**. _Clique com o botão direito_ e escolhe a opção **Selecionar Visualização**, agora selecione o ícone da nuvem de palavras, como na imagem a seguir. 
   ![Nuvem de Palavras](images/Tag1.png)
   ![Nuvem de Palavras](images/Tag2.png)

6. Usar uma visualização como filtro. Ao lado do título da visualização existe um filtro, selecione para o **filtro ficar verde**, isso significa que a **visualização está sendo utilizada como filtro**
   ![Nuvem de Palavras como Filtro](images/Tag3.png)

7. Selecione algum item da Nuvem de Palavras, vai perceber que todas as visualizações vão ser filtradas a partir dela. Como exemplo foi selecionado **Outros**.
   ![Nuvem de Palavras como Filtro](images/Tag4.png)

8. Adicionar Título na primeira página do Painel. Na primeira Coluna selecione o segundo ícone do gráfico (Visualizações). Escolha **Caixa de Texto** segure e arrasta para a Tela no canto superior da tela. 
   ![Título do Painel](images/Titulo.png)

9. Personalize o Título mudando as propriedades, segunda coluna segundo ícone, adicione uma cor ao fundo, deixe o texto centralizado e outras personalizações como mostra na imagem a seguir.
   ![Título do Painel](images/Titulo2.png)

### **Variedade de Filtros**
10. Adicionar uma Caixa de Filtro na Tela, selecione o campo **Ano** para utilizar como Filtro, arraste e solte até ficar ao lado do Título, canto direito superior.  
   ![Filtro Seletor](images/Filtro10.png)

11. Na gramática do Painel, selecione o tipo de visualização que quer **Filtros do Painel de Controle**. E selecione um Ano do Filtro.
   ![Filtro Seletor](images/Filtro11.png)
   ![Filtro Seletor](images/Filtro12.png)

12. Personalize o nome do Filtro, selecione na segunda coluna no segundo ícone (Propriedades), Atualize o Label para **Personalizado**, e deixe como **ANO**.
   ![Filtro Seletor](images/Filtro13.png)   

13. Também pode utilizar filtros no cabeçalho do Painel. Selecione o campo **ESTADO** na primeira coluna no primeiro ícone (Dado). Segure e arraste para o campo superior da tela onde há um '+' com Clique aqui ou arraste os dados para adicionar um filtro".
   ![Filtro Seletor](images/Filtro15.png)   

14. Faça o mesmo com o campo **EMBARCACAO**. 
   ![Filtro Seletor](images/Filtro16.png)  

15. Renomeie o nome da Tela 1 para **'Geral'** 
   ![Tela 1 para Geral](images/Geral.png)  

## 4️⃣ Adição de Previsão e Campo Calculado

1. Adiocione mais uma tela. No canto inferior tem um símbolo de '+'. Clique nele para adicionar uma segunda Tela.
   ![Tela 2](images/Tela2.png) 

2. Segure _CTRL+Clique_ nos campos **ANO e QUANTIDADE** na primeira coluna no primeiro ícone (Dados), selecione e arraste os dois para a tela em branco. Verifique que é um gráfico de **Linha**.
   ![Previsão](images/Previsao.png) 

3. Seleciona a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolhe a opção **Previsão**.
   ![Previsão](images/Previsao2.png) 
   ![Previsão](images/Previsao3.png) 

4. (OPCIONAL) Personalizar a propriedade do gráfico, deixando o valor e o ponto no gráfico visível. 
   ![Propriedades da Visualização](images/Prop1.png) 
   ![Propriedades da Visualização](images/Prop2.png) 





## 5️⃣ [EXTRA] Embeddings com OCI Generative AI

### ❓**O que são Embeddings?**
> Embeddings são representações vetoriais de objetos, como textos ou imagens. **Ao transformar objetos em vetores, conseguimos realizar operações matemáticas que permitem comparar, analisar e calcular a similaridade entre eles.** Isso possibilita, por exemplo, identificar semelhanças entre textos ou buscar informações relevantes de forma eficaz.

### 🔍 **Por que Embeddings são importantes?**
>   - **Análise de Similaridade:** Com embeddings, podemos calcular a proximidade entre diferentes objetos, facilitando a identificação de itens semelhantes.
>    - **Eficiência Computacional:** Representar dados em vetores torna o processamento de informações mais rápido e eficiente.
>    - **Versatilidade:** Embeddings podem ser usados em vários contextos, como busca de informações, recomendação de conteúdo, entre outros.

Vamos acessar o Serviço de OCI Generative AI. A forma mais simples de fazer isto é pesquisando por
**“Generative AI”** na aba de busca:

   ![Search Generative AI](images/search-genai.png " ")

Uma vez dentro do serviço, vamos selecionar **“Embedding”**, no menu do canto esquerdo, abaixo de **“Playground”**.

   ![Acess Playground](images/genai-playground-acess.png " ")



## Agradecimentos

- **Autores** - Gabriela Miyazima
- **Autor Contribuinte** - Caio Oliveira, Isabelle Anjos
- **Última Atualização Por/Data** - Janeiro 2025

## Declaração de Porto Seguro (Safe Harbor)

O texto a seguir tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 
