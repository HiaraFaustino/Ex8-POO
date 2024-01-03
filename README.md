Deseja-se implementar um sistema para emissão de folhas de pagamento para os
funcionários de uma universidade. Para fins de pagamento, existem apenas 2 classes de
funcionários: professores e técnicos administrativos. Ambas as classes possuem
atributos comuns, tais como código e nome. Entretanto, os professores são todos
horistas, sendo o salário de um professor calculado da seguinte forma: salarioHora *
nroAulas. Já os técnicos administrativos possuem um salário mensal fixo. Para realizar
o pagamento de salário, existe uma ficha mensal para cada funcionário chamada
PontoFunc. Nesta ficha consta o número de ausências (faltas) e de atrasos de cada
funcionário em um dado mês de um dado ano. Para os professores, uma falta significa
uma ausência em uma dada aula. Para os técnicos administrativos, uma falta significa
uma ausência em um dia de trabalho. Com base nessas informações chega-se às
seguintes fórmulas para o cálculo do salário de professores e técnicos administrativos:
salarioProf = salarioHora * nroAulas – salarioHora * nroFaltas
salarioTec = salarioMensal – ((salarioMensal/30) * nroFaltas
Além do salário, os funcionários recebem também um bônus por pontualidade. Os
professores sem nenhum atraso recebem 10% do salário líquido mensal, enquanto os
técnicos administrativos pontuais recebem 8% do salário líquido. Para cada atraso
registrado, o funcionário perde um ponto percentual do seu bônus.
Para um dado funcionário, seja ele professor ou técnico administrativo, deve ser
impresso em sua folha de pagamento mensal as seguintes informações: código, nome,
salário líquido e bônus.
Com base nessas informações, foi realizada a modelagem exibida no final da prova.
Esta modelagem explora os relacionamentos de herança e facilita o uso de
polimorfismo. Nesta prova, você deve implementar as classes dessa modelagem,
seguindo à risca o modelo de domínio apresentado. O código de teste a seguir deve
executar sem erros a fim de validar sua implementação.
if __name__ == "__main__":
  funcionarios = []
  prof = Professor(1, "Joao", "Doutor", 45.35, 32)
  prof.adicionaPonto(4, 2021, 0, 0)
  prof.lancaFaltas(4, 2021, 2)
  prof.lancaAtrasos(4, 2021, 3)
  funcionarios.append(prof)
  tec = TecAdmin(2, "Pedro", "Analista Contábil", 3600)
  tec.adicionaPonto(4, 2021, 0, 0)
  tec.lancaFaltas(4, 2021, 3)
  tec.lancaAtrasos(4, 2021, 4)
  funcionarios.append(tec)
  for func in funcionarios:
    func.imprimeFolha(4, 2021)
    print()
Para os dados de entrada utilizados, o método imprimeFolha deve produzir o seguinte
resultado:
Código : 1
Nome Joao
Salário liquido: 1360.50
Bonus: 95.24

Código 2: 2
Nome: Pedro
Salário líquido: 3240.00
Bonus: 129.60
