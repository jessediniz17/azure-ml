# Trabalhando com Machine Learning
Nosso primeiro passo é criar um resource de machine learning, o qual você pode encontrar no marketplace do Azure, procurando por Azure Machine Learning. Em seguida, é necessário criar um workspace, para podermos trabalhar. No workspace, criaremos um novo trabalho de ML automatizado, opção essa que você pode localizar no menu lateral.

Durante a criação desse processo, na terceira etapa, o tipo de tarefa escolhido deve ser "Regressão". Ainda nessa etapa, crie um ativo de dados. Escolha a opção *De arquivos da Web* e cole o link a seguir:

https://aka.ms/bike-rentals

Na etapa seguinte, na opção de cabeçalhos, apenas o primeiro arquivo tem cabeçalho. Avance nas opções seguintes. 

Voltaremos para a quarta etapa de criação do modelo ML automatizado. Em *Coluna de destino*, selecione a opção *Rentals*. Há uma opção de configurações adicionais. Desmarque as opções selecionadas. Em Modelos Permitidos, selecione *RandomForest e LightGBM*.

Em Limites, preencha com os seguintes dados:

3

3

3

0,085

15

15



Em tipo de validação, selecione a opção *Divisão de validação de treinamento*



Avance nas etapas seguintes e aguarde o arquivo ser executado. Quando o processo for concluído, você pode checá-lo no menu *Tarefas*. Abra a tarefa e adicione um modelo de registro. Após isso, vá no menu lateral e procure por *Pontos de extremidade*. Na aba *Testar*, utilizei o Json abaixo

{
  "input_data": {
    "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]
  }
}
