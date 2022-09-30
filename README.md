# Modelagem do banco de dados

Repositório para modelagem do banco de dados. 


# Mapa Conceitual
![](bdconceitual1.png)

## Descrição das tabelas do modelo conceitual

------------------------------------------------------------------------------------------------------------------------------------------------


## _Entidade aluno_
A entidade aluno serve para identificar e guardar os dados de um determinado aluno da universidade, tendo como seu identificador a matrícula (MAT). A entidade se relaciona com histórico, possuindo cardinalidade de 1,1, já que, um aluno pode ter apenas um histórico, tal qual um histórico pode ter apenas um aluno.
Seus atributos são: MAT (número da matrícula), nome (nome completo do aluno), endereço e cidade(endereço e cidade em que o aluno reside).

------------------------------------------------------------------------------------------------------------------------------------------------

## _Entidade historico_
O histórico possui a utilidade de guardar dados escolares de um determinado aluno, tal como turma, disciplinas e professores que o mesmo veio a ter. Deste modo se faz necessário a ligação (relacionamento) entre eles. Quanto à cardinalidade dos relacionamentos, exceto de aluno (como já foi esclarecido anteriormente), serão 1,n, tendo em vista que, por ser somente um histórico para um aluno, as turmas, disciplinas e professores aparecerão também nos históricos de outros alunos. Ex: 1 disciplina pode aparecer em n históricos, já que não existe somente um aluno.
Seus atributos são: frequência e nota.

------------------------------------------------------------------------------------------------------------------------------------------------

## _Entidade turma_
Responsável por armazenar dados da turma, tais como (atributos): código da turma, ano (ano em que a turma cursa) e horário(calendário de aulas). A turma se relaciona com disciplinas (uma ou mais), pois a turma as estuda; e professores (um ou mais), que são responsáveis por lecionarem as aulas.

------------------------------------------------------------------------------------------------------------------------------------------------

## _Entidade disciplinas_
Armazena dados sobre as disciplinas da universidade, como por exemplo os seguintes atributos: código da disciplina, nome da disciplina (português. matemática, etc) e sua carga horária. Se relaciona com histórico, como já foi citado anteriormente e com turma, podendo estar presente em uma ou mais turmas (1,n).

------------------------------------------------------------------------------------------------------------------------------------------------

## _Entidade professores_
Guarda as informações pessoais dos professores como (atributos): código do professor, nome (nome completo do professor), endereço e cidade (endereço e cidade em que o aluno reside). Se relaciona com histórico, como mencionado acima, e também com turma, podendo ter uma ou mais (1,n).

------------------------------------------------------------------------------------------------------------------------------------------------



# Mapa Lógico
![](bdlogico1.png)

## Descrição das tabelas do modelo lógico

------------------------------------------------------------------------------------------------------------------------------------------------

## _Tabela Alunos_Historico_
A tabela _alunos_historico_ é a base de dados para manter alguns dados pessoais dos alunos da universidade e algumas informações sobre como a universidade administra seu historico. Nela possuímos os atributos/colunas:

•endereco: endereço do aluno

•nome: nome do aluno

•MAT: chave primária da tabela

•cidade: cidade do aluno

•nota: nota do aluno guardada no historico

•frequencia: frequencia do aluno guardada no historico

•fk_turma_COD_TURMA: chave estrangeira que faz referência a tabela _turma_

•fk_turma_ANO: chave estrangeira que faz referência a tabela _turma_

•fk_disciplina_COD_DISC: chave estrangeira que faz referência a tabela _disciplina_

•fk_professores_COD_PROF: chave estrangeira que faz referência a tabela _referência_

------------------------------------------------------------------------------------------------------------------------------------------------

## _Tabela Professores_
A tabela _professores_, assim como na tabela _alunos_historico_, será a base de dados para manter alguns dados pessoais dos professores da universidade. Nela possuímos os atributos/colunas:

•nome: nome do professor

•COD_PROF: chave primária da tabela

•cidade: cidade onde se encontra o professor

•endereco: endereço atual em que reside o professor

------------------------------------------------------------------------------------------------------------------------------------------------

## _Tabela Turma_
Na tabela _turma_ é mostrado algumas informações armazenadas das turmas da faculdade. Nela possuímos os atributos/colunas:

•COD_TURMA: chave primária da tabela

•ANO: chave primária da tabela

•horário: calendário de aulas 

•fk_disciplinas_COD_DISC: chave estrangeira que faz referência a tabela _disciplinas_

•fk_professores_COD_PROF: chave estrangeira que faz referência a tabela _professores_

------------------------------------------------------------------------------------------------------------------------------------------------

## _Tabela Disciplinas_
A tabela _disciplinas_ trás informações armazenadas sobre horarios e nomes das disciplinas apresentadas na universidade.

•COD_DISC: chave primária da tabela

•nome_disc: nomes das disciplinas

•carga_hor: carga horaria de disciplinas
