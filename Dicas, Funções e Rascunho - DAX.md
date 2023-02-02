# DAX

Funções e operações DAX.

### Coluna ano
NOVA_COLUNA = YEAR('tabela'[COLUNA_DATA])

### Aplicando Soma
NOVA_COLUNA = SUM('tabela'[COLUNA])

### Operação com duas colunas
NOVA_COLUNA = 'tabela'[COLUNA_A] + 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] / 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] - 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] * 'tabela2'[COLUNA_B]

### Operação condicional SWITCH
NOVA_COLUNA = SWITCH([COLUNA_A], 1, "Jan", 2, "Fev", 3, March", "Outra") 

### Operação condicional IF
NOVA_COLUNA = IF( 'tabela'[COLUNA_A] < 500, VERDADEIRO, FALSO)
NOVA_COLUNA = IF( 'tabela'[COLUNA_A] < 500, "x", "y")

obs.: BLANK() == VAZIO

### Medidas e colunas

payment_tax_ok = IF(payments[payment_fee] = BLANK(), 0, payments[payment_fee]/payments[payment_amount])

payment_high_avg = CALCULATE(COUNT(payments[payment_id]), FILTER(payments, payments[payment_tax_ok]>AVERAGE(payments[payment_tax_ok])))

payment_low_avg = CALCULATE(COUNT(payments[payment_id]), FILTER(payments, payments[payment_tax_ok]<AVERAGE(payments[payment_tax_ok])))

##### Total somado, ignorando os filtros de methods - ALL()
Total = CALCULATE(SUM(payments[payment_amount), ALL(payments['payment_method']))

-----------------------------------------------
### Criar Tabela 'Date'
date = GENERATE( CALENDAR("2020-01-01", TODAY()), VAR currentDay = [Date] VAR day = DAY(currentDay) VAR month = MONTH(currentDay) VAR year = YEAR(currentDay) RETURN ROW ("day", day, "month", month, "year", year))

* gera coluna date
- CALENDAR("2020-01-01", TODAY()) 

* Atribui coluna Date a currentDay
- VAR currentDay = [Date] 

* Extrai o Dia da coluna currentDay
- VAR day = DAY(currentDay)

* Extrai o Mês da coluna currentDay
- VAR month = MONTH(currentDay)

* Extrai o Ano da coluna currentDay
- VAR year = YEAR(currentDay)

# Rabiscos

duration_ok = if(netflix_titles_2021[type] = "TV SHOW", left(netflix_titles_2021[duration],len(netflix_titles_2021[duration])-7),left(netflix_titles_2021[duration],len(netflix_titles_2021[duration])-4))

TIME_DAX = SEARCH(" ", netflix_titles_2021[duration]) - 1

acao = IF(dataset_netflix_titles_2021[type]="Movie", CONTAINSSTRING(dataset_netflix_titles_2021[listed_in], "action"), False)

acao = CONTAINSSTRING(dataset_netflix_titles_2021[listed_in], "action")