# DAX

Funções e operações DAX.

#### Coluna ano
NOVA_COLUNA = YEAR('tabela'[COLUNA_DATA])

#### Aplicando Soma
NOVA_COLUNA = SUM('tabela'[COLUNA])

#### Operação com duas colunas
NOVA_COLUNA = 'tabela'[COLUNA_A] + 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] / 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] - 'tabela2'[COLUNA_B]
NOVA_COLUNA = 'tabela'[COLUNA_A] * 'tabela2'[COLUNA_B]

#### Operação condicional SWITCH
NOVA_COLUNA = SWITCH([COLUNA_A], 1, "Jan", 2, "Fev", 3, March", "Outra") 

#### Operação condicional IF
NOVA_COLUNA = IF( 'tabela'[COLUNA_A] < 500, VERDADEIRO, FALSO)
NOVA_COLUNA = IF( 'tabela'[COLUNA_A] < 500, "x", "y")

obs.: BLANK() == VAZIO
EVALUATE { COALESCE(BLANK(), 10, DATE(2008, 3, 3)) }