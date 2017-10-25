# Data for fludashboard
Aggregate data generated and consumed by FluVigilanciaBR surveillance tools

## sqlite Database tables

- localidades: Table with localities code, abbreviation, and name. Columns:
  - 'codigo', 'sigla', 'nome'
  
- serie_temporal: Table with weekly aggregated notification data, used to generate the notification curve on 
the the time series panel. Columns:
  - 'código', 'epiyear', 'epiweek', 'dado', 'escala', 'registros', 'data de execução'

- situacao: Table with data status for each week. Used to determine when to stop drawing the notification curve, and 
also to define the color of each location based on the probability of being at each activity level. Columns:
  - 'código', 'epiyear', 'epiweek', 'situação', 'baixa', 'epidêmica', 'alta', 'muito alta', 'data de execução'

- estimativas: Table with estimates generated. Used to draw the point estimate curve, lower and upper confidence 
intervals, both for the most recent data as well as in retrospective, based on base_epiyear and base_epiweek columns.
 Columns:
  - 'código', 'base_epiyear', 'base_epiweek',
            'epiyear', 'epiweek', 'dado', 'escala', 'registros',
            'mediana', 'limite inferior', 'limite superior',
            'baixa', 'epidêmica', 'alta', 'muito alta',
            'data de execução'
            
- faixa_etaria_e_genero: Table with weekly notifications aggregated by age bracket and gender. Used to draw histogram
 panel. Columns:
  - 'código', 'epiyear', 'epiweek', 'dado', 'escala', 'sexo', '< 2 anos', '2-4 anos', '0-4 anos', '5-9 anos',
            '10-19 anos', '20-29 anos', '30-39 anos', '40-49 anos', '50-59 anos', '60+ anos'
            
- limiares: Table with activity levels for each locality. Used to draw activity thresholds. Columns:
  - 'código', 'dado', 'escala', 'limiar pré-epidêmico', 'intensidade alta', 'intensidade muito alta'
  
- corredores: Table with typical activity levels. Used to draw background on the time series panel. Columns:
  - 'código', 'epiweek', 'dado', 'escala', 'corredor baixo', 'corredor mediano', 'corredor alto'
