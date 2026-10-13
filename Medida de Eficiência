Disciplina: Programação para Dispositivos Móveis
Professora: Layse Santos Souza
Nome do Aluno: Christian Gonçalves Dantas
Medida de Eficiência - Unidade I

Questão 1) Dado o seguinte mapa de preços de bolos: const boloPrecos = {'ovos' : 5,5, 'chocolate' : 7,5, 'cenoura' : 6,5, }; Escreva um programa em Dart para calcular o total para um determinado pedido. Por exemplo, dada a ordem const ordem = ['ovos', 'chocolate']; o programa deve imprimir -> Total = 13.0. OBS.: Se um bolo não estiver no cardápio, o programa deve imprimir algo assim -> limão não está no cardápio.
void main() {
  var boloPrecos = {'ovos': 5.5, 'chocolate': 7.5, 'cenoura': 6.5};
  var ordem = ['ovos', 'chocolate'];
  double total = 0;
 
  for (var bolo in ordem) {
    if (boloPrecos.containsKey(bolo)) {
      total = total + boloPrecos[bolo]!;
    } else {
      print('$bolo não está no cardápio');
    }
  }
 
  print('Total = $total');
}
Questão 2) Faça um algoritmo para ler o número de termos e calcular o valor da série abaixo: S = 3^4!/5 + 5^8!/10 + 7^12!/15 – 9^16!/20 + 11^20!/25 – 13^24!/30 + 15^28!/35 ...
import 'dart:io';
import 'dart:math';
 
double fat(int n) {
  double f = 1;
  for (int i = 1; i <= n; i++) {
    f = f * i;
  }
  return f;
}
 
void main() {
  print('Digite o numero de termos:');
  int n = int.parse(stdin.readLineSync()!);
 
  double s = 0;
  int base = 3;
  int exp = 4;
  int den = 5;
 
  for (int i = 1; i <= n; i++) {
    double termo = pow(base, fat(exp)) / den;
    if (i >= 4 && i % 2 == 0) {
      s = s - termo;
    } else {
      s = s + termo;
    }
    base = base + 2;
    exp = exp + 4;
    den = den + 5;
  }
 
  print('S = $s');
}
Questão 3) Faça um algoritmo que imprima a série abaixo, o número de termos será lido. S = 1 5 100 2 10 90 4 15 80 8 20 70 16 25 60 32 30 50 64 35 40 128 40 30 256 ...
import 'dart:io';
 
void main() {
  print('Digite o numero de termos:');
  int n = int.parse(stdin.readLineSync()!);
 
  int a = 1;
  int b = 5;
  int c = 100;
 
  for (int i = 1; i <= n; i++) {
    if (i % 3 == 1) {
      stdout.write('$a ');
      a = a * 2;
    } else if (i % 3 == 2) {
      stdout.write('$b ');
      b = b + 5;
    } else {
      stdout.write('$c ');
      c = c - 10;
    }
  }
  print('');
}
Questão 4) Elabore um algoritmo para ler a matrícula, nome, sexo (“M” e “F”), três notas e o número de faltas dos alunos de uma escola, onde o FLAG é a matrícula = ’00000’. E imprima: a) A média da turma. b) O percentual de alunos aprovados. c) A matrícula do aluno do sexo masculino e feminino que possui a maior média e que foi aprovado. d) A média dos alunos do sexo feminino. Obs: Considere para aprovação a média 7,0 e o limite de faltas 18.
import 'dart:io';
 
void main() {
  int total = 0, aprovados = 0, contF = 0;
  double somaMedias = 0, somaF = 0;
  double maiorM = 0, maiorF = 0;
  String matM = '', matF = '';
 
  print('Matricula (00000 para sair):');
  String mat = stdin.readLineSync()!;
 
  while (mat != '00000') {
    print('Nome:');
    String nome = stdin.readLineSync()!;
    print('Sexo (M/F):');
    String sexo = stdin.readLineSync()!.toUpperCase();
    print('Nota 1:');
    double n1 = double.parse(stdin.readLineSync()!);
    print('Nota 2:');
    double n2 = double.parse(stdin.readLineSync()!);
    print('Nota 3:');
    double n3 = double.parse(stdin.readLineSync()!);
    print('Faltas:');
    int faltas = int.parse(stdin.readLineSync()!);
 
    double media = (n1 + n2 + n3) / 3;
    total++;
    somaMedias = somaMedias + media;
 
    if (media >= 7 && faltas <= 18) {
      aprovados++;
      if (sexo == 'M' && media > maiorM) {
        maiorM = media;
        matM = mat;
      }
      if (sexo == 'F' && media > maiorF) {
        maiorF = media;
        matF = mat;
      }
    }
 
    if (sexo == 'F') {
      contF++;
      somaF = somaF + media;
    }
 
    print('Matricula (00000 para sair):');
    mat = stdin.readLineSync()!;
  }
 
  print('Media da turma: ${(somaMedias / total).toStringAsFixed(2)}');
  double perc = aprovados / total * 100;
  print('Percentual de aprovados: ${perc.toStringAsFixed(1)}%');
  print('Maior media aprovado (M): $matM');
  print('Maior media aprovada (F): $matF');
  if (contF > 0) {
    print('Media do sexo feminino: ${(somaF / contF).toStringAsFixed(2)}');
  }
}
Questão 5) Faça um algoritmo para ler o Nome, Sexo (M ou F) e o peso dos recém-nascidos de uma maternidade e de acordo com a tabela abaixo imprima: a) Para cada recém-nascido: o nome, o sexo e a classificação quanto ao peso. b) O nome do recém-nascido do sexo feminino com o maior peso. c) O percentual de recém-nascidos em cada classificação de peso. (0 <= Peso <= 2 kg: Baixo Peso; 2 < Peso <= 4 kg: Normal; Acima de 4 kg: Alto Peso)
import 'dart:io';
 
void main() {
  int total = 0, baixo = 0, normal = 0, alto = 0;
  double maiorPesoF = 0;
  String nomeF = '';
 
  print('Nome do bebe (FIM para sair):');
  String nome = stdin.readLineSync()!;
 
  while (nome != 'FIM') {
    print('Sexo (M/F):');
    String sexo = stdin.readLineSync()!.toUpperCase();
    print('Peso:');
    double peso = double.parse(stdin.readLineSync()!);
 
    String classif;
    if (peso <= 2) {
      classif = 'Baixo Peso';
      baixo++;
    } else if (peso <= 4) {
      classif = 'Normal';
      normal++;
    } else {
      classif = 'Alto Peso';
      alto++;
    }
    total++;
 
    print('$nome - $sexo - $classif');
 
    if (sexo == 'F' && peso > maiorPesoF) {
      maiorPesoF = peso;
      nomeF = nome;
    }
 
    print('Nome do bebe (FIM para sair):');
    nome = stdin.readLineSync()!;
  }
 
  print('Menina com maior peso: $nomeF');
  print('Baixo Peso: ${(baixo / total * 100).toStringAsFixed(1)}%');
  print('Normal: ${(normal / total * 100).toStringAsFixed(1)}%');
  print('Alto Peso: ${(alto / total * 100).toStringAsFixed(1)}%');
}
Questão 6) Levando em consideração que a função Random(N) gera um número aleatório entre 1 e N, faça um algoritmo que gere um número aleatório entre 1 e 100. E, então, permita que o usuário digite números, neste intervalo, até que acerte o número gerado. A cada número digitado, o novo intervalo deverá ser impresso, limitando os valores a serem chutados. Ex: se o número for 23 e o usuário digitar 40, deverá ser impresso “O número está entre 0 e 40”.
import 'dart:io';
import 'dart:math';
 
void main() {
  int numero = Random().nextInt(100) + 1;
  int min = 0;
  int max = 100;
  int chute = 0;
 
  while (chute != numero) {
    print('Digite um numero entre $min e $max:');
    chute = int.parse(stdin.readLineSync()!);
 
    if (chute > numero) {
      max = chute;
      print('O número está entre $min e $max');
    } else if (chute < numero) {
      min = chute;
      print('O número está entre $min e $max');
    }
  }
 
  print('Acertou! O numero era $numero');
}
Questão 7) Leia o número de termos e calcule o valor da seguinte série: S = X²/1! + X³/2! + X⁴/3! + X⁵/4! + X⁶/3! + X⁷/2! + X⁸/1! + X⁹/2! + X¹⁰/3! + X¹¹/4! ...
import 'dart:io';
import 'dart:math';
 
int fat(int n) {
  int f = 1;
  for (int i = 1; i <= n; i++) {
    f = f * i;
  }
  return f;
}
 
void main() {
  print('Valor de X:');
  double x = double.parse(stdin.readLineSync()!);
  print('Numero de termos:');
  int n = int.parse(stdin.readLineSync()!);
 
  double s = 0;
  int d = 1;
  int passo = 1;
 
  for (int i = 1; i <= n; i++) {
    s = s + pow(x, i + 1) / fat(d);
    if (d == 4) passo = -1;
    if (d == 1) passo = 1;
    d = d + passo;
  }
 
  print('S = $s');
}
Questão 8) A Universidade Tiradentes estará realizando o Concurso Vestibular para os cursos de Ciência da Computação e Sistemas de Informação. Para cada candidato são lidos: a) Código (FLAG ’0000’) b) Curso (CC ou SI) c) Nome d) Sexo e) Pontuação (0-5000). Informações desejadas: a) O código, nome e pontuação dos candidatos, independente do sexo, do curso de Ciência da Computação que fizeram mais de 2500 pontos. b) O nome do candidato do sexo masculino que teve a menor pontuação geral. c) O código do candidato do sexo masculino que teve a maior pontuação para o curso de Sistemas de Informação. d) O percentual geral de candidatos do sexo Masculino e Feminino inscritos no vestibular.
import 'dart:io';
 
void main() {
  int total = 0, masc = 0, fem = 0;
  int menorM = 5001;
  String nomeMenorM = '';
  int maiorSI = -1;
  String codMaiorSI = '';
  List<String> listaCC = [];
 
  print('Codigo (0000 para sair):');
  String cod = stdin.readLineSync()!;
 
  while (cod != '0000') {
    print('Curso (CC/SI):');
    String curso = stdin.readLineSync()!.toUpperCase();
    print('Nome:');
    String nome = stdin.readLineSync()!;
    print('Sexo (M/F):');
    String sexo = stdin.readLineSync()!.toUpperCase();
    print('Pontuacao:');
    int pontos = int.parse(stdin.readLineSync()!);
 
    total++;
 
    if (curso == 'CC' && pontos > 2500) {
      listaCC.add('$cod - $nome - $pontos');
    }
 
    if (sexo == 'M') {
      masc++;
      if (pontos < menorM) {
        menorM = pontos;
        nomeMenorM = nome;
      }
      if (curso == 'SI' && pontos > maiorSI) {
        maiorSI = pontos;
        codMaiorSI = cod;
      }
    } else {
      fem++;
    }
 
    print('Codigo (0000 para sair):');
    cod = stdin.readLineSync()!;
  }
 
  print('Candidatos de CC com mais de 2500 pontos:');
  for (var c in listaCC) {
    print(c);
  }
  print('Homem com menor pontuacao: $nomeMenorM');
  print('Codigo do homem com maior pontuacao em SI: $codMaiorSI');
  print('Masculino: ${(masc / total * 100).toStringAsFixed(1)}%');
  print('Feminino: ${(fem / total * 100).toStringAsFixed(1)}%');
}
Questão 9) Existem números que têm a seguinte característica: 3025 = 30 + 25 = 55 * 55 = 3025. Faça um algoritmo para imprimir todos os números entre 1000 e 9999 que tenham tal característica.
void main() {
  for (int n = 1000; n <= 9999; n++) {
    int parte1 = n ~/ 100;
    int parte2 = n % 100;
    int soma = parte1 + parte2;
 
    if (soma * soma == n) {
      print(n);
    }
  }
}
Questão 10) Uma empresa decidiu fazer um levantamento sobre o perfil de candidatos que se apresentarem para o preenchimento de vagas. Para cada candidato serão solicitados o nome, o sexo, a idade e se tem ou não experiência no serviço. O Flag é o nome FIM. Calcular e imprimir: a) O número de candidatos do sexo feminino e masculino. b) A idade média dos homens que já têm experiência no serviço. c) A porcentagem dos homens com mais de 45 anos com relação ao total de homens. d) O número de mulheres com idade inferior a 30 anos e com experiência no serviço. e) O nome da candidata com a menor idade que já tem experiência no serviço.
import 'dart:io';
 
void main() {
  int homens = 0, mulheres = 0;
  int homensExp = 0, somaIdadeExp = 0;
  int homens45 = 0;
  int mulheres30 = 0;
  int menorIdade = 200;
  String nomeMenor = '';
 
  print('Nome (FIM para sair):');
  String nome = stdin.readLineSync()!;
 
  while (nome != 'FIM') {
    print('Sexo (M/F):');
    String sexo = stdin.readLineSync()!.toUpperCase();
    print('Idade:');
    int idade = int.parse(stdin.readLineSync()!);
    print('Tem experiencia? (S/N):');
    String exp = stdin.readLineSync()!.toUpperCase();
 
    if (sexo == 'M') {
      homens++;
      if (exp == 'S') {
        homensExp++;
        somaIdadeExp = somaIdadeExp + idade;
      }
      if (idade > 45) {
        homens45++;
      }
    } else {
      mulheres++;
      if (exp == 'S') {
        if (idade < 30) {
          mulheres30++;
        }
        if (idade < menorIdade) {
          menorIdade = idade;
          nomeMenor = nome;
        }
      }
    }
 
    print('Nome (FIM para sair):');
    nome = stdin.readLineSync()!;
  }
 
  print('Mulheres: $mulheres');
  print('Homens: $homens');
  if (homensExp > 0) {
    print('Idade media homens com experiencia: ${somaIdadeExp / homensExp}');
  }
  if (homens > 0) {
    double perc = homens45 / homens * 100;
    print('Homens com mais de 45 anos: ${perc.toStringAsFixed(1)}%');
  }
  print('Mulheres com menos de 30 anos e com experiencia: $mulheres30');
  print('Candidata mais nova com experiencia: $nomeMenor');
}
Questão 11) Faça um algoritmo para ler o código, nome, sexo e número de horas de aula dadas no mês dos professores de uma Universidade, sabendo que por cada hora de aula um professor ganha R$ 12,30. Emita uma listagem contendo o código, nome, salário bruto e salário líquido de todos os professores lidos e no final imprima a média dos salários líquidos de cada sexo. Observações: o desconto para os homens é 10% e para as mulheres é 5%; o FLAG é o código ’9999’.
import 'dart:io';
 
void main() {
  double somaM = 0, somaF = 0;
  int contM = 0, contF = 0;
  List<String> lista = [];
 
  print('Codigo (9999 para sair):');
  String cod = stdin.readLineSync()!;
 
  while (cod != '9999') {
    print('Nome:');
    String nome = stdin.readLineSync()!;
    print('Sexo (M/F):');
    String sexo = stdin.readLineSync()!.toUpperCase();
    print('Horas de aula no mes:');
    double horas = double.parse(stdin.readLineSync()!);
 
    double bruto = horas * 12.30;
    double liquido;
 
    if (sexo == 'M') {
      liquido = bruto - bruto * 0.10;
      somaM = somaM + liquido;
      contM++;
    } else {
      liquido = bruto - bruto * 0.05;
      somaF = somaF + liquido;
      contF++;
    }
 
    String b = bruto.toStringAsFixed(2);
    String l = liquido.toStringAsFixed(2);
    lista.add('$cod - $nome - Bruto: $b - Liquido: $l');
 
    print('Codigo (9999 para sair):');
    cod = stdin.readLineSync()!;
  }
 
  for (var p in lista) {
    print(p);
  }
 
  if (contM > 0) {
    print('Media salario liquido homens: ${(somaM / contM).toStringAsFixed(2)}');
  }
  if (contF > 0) {
    print('Media salario liquido mulheres: ${(somaF / contF).toStringAsFixed(2)}');
  }
}
Questão 12) Escreva um algoritmo que leia um número e o imprima de trás para frente. Exemplo: 6042 (impressão: 2406).
import 'dart:io';
 
void main() {
  print('Digite um numero:');
  int num = int.parse(stdin.readLineSync()!);
  String invertido = '';
 
  while (num > 0) {
    invertido = invertido + (num % 10).toString();
    num = num ~/ 10;
  }
 
  print(invertido);
}
Questão 13) Faça um algoritmo para ler um conjunto N de números inteiros e imprimir cada elemento do conjunto e quantas vezes ele se repete. Ex.: vetor lido 3 8 5 3 8 7 3 7 3 7 → resultado 3–4, 8–2, 5–1, 7–3. OBS.: O valor de N será lido.
import 'dart:io';
 
void main() {
  print('Quantos numeros?');
  int n = int.parse(stdin.readLineSync()!);
  List<int> v = [];
 
  for (int i = 0; i < n; i++) {
    print('Numero ${i + 1}:');
    v.add(int.parse(stdin.readLineSync()!));
  }
 
  for (int i = 0; i < n; i++) {
    bool repetido = false;
    for (int j = 0; j < i; j++) {
      if (v[j] == v[i]) {
        repetido = true;
      }
    }
 
    if (repetido == false) {
      int cont = 0;
      for (int k = 0; k < n; k++) {
        if (v[k] == v[i]) {
          cont++;
        }
      }
      print('${v[i]} - $cont');
    }
  }
}
Questão 14) Faça um algoritmo que leia o tamanho e os elementos de dois vetores ordenados e, em seguida, gere um terceiro vetor também ordenado. Obs: o usuário deverá digitar os dois vetores obrigatoriamente.
import 'dart:io';
 
void main() {
  print('Tamanho do vetor A:');
  int t1 = int.parse(stdin.readLineSync()!);
  List<int> a = [];
  for (int i = 0; i < t1; i++) {
    print('A[$i] (em ordem crescente):');
    a.add(int.parse(stdin.readLineSync()!));
  }
 
  print('Tamanho do vetor B:');
  int t2 = int.parse(stdin.readLineSync()!);
  List<int> b = [];
  for (int i = 0; i < t2; i++) {
    print('B[$i] (em ordem crescente):');
    b.add(int.parse(stdin.readLineSync()!));
  }
 
  List<int> c = [];
  int i = 0, j = 0;
 
  while (i < t1 && j < t2) {
    if (a[i] < b[j]) {
      c.add(a[i]);
      i++;
    } else {
      c.add(b[j]);
      j++;
    }
  }
  while (i < t1) {
    c.add(a[i]);
    i++;
  }
  while (j < t2) {
    c.add(b[j]);
    j++;
  }
 
  print('Vetor C: $c');
}
Questão 15) Faça um algoritmo para ler o número e o peso de N bois de uma fazenda, armazene estes dados em um vetor e, em seguida, possibilite que sejam feitas várias pesquisas, onde o fazendeiro digitará um intervalo para os pesos e, então, o algoritmo deve fornecer uma impressão de todos os bois com peso dentro desse intervalo.
import 'dart:io';
 
void main() {
  print('Quantos bois?');
  int n = int.parse(stdin.readLineSync()!);
  List<int> numero = [];
  List<double> peso = [];
 
  for (int i = 0; i < n; i++) {
    print('Numero do boi:');
    numero.add(int.parse(stdin.readLineSync()!));
    print('Peso do boi:');
    peso.add(double.parse(stdin.readLineSync()!));
  }
 
  String resp = 'S';
  while (resp == 'S') {
    print('Peso minimo:');
    double min = double.parse(stdin.readLineSync()!);
    print('Peso maximo:');
    double max = double.parse(stdin.readLineSync()!);
 
    for (int i = 0; i < n; i++) {
      if (peso[i] >= min && peso[i] <= max) {
        print('Boi ${numero[i]} - ${peso[i]} kg');
      }
    }
 
    print('Fazer outra pesquisa? (S/N)');
    resp = stdin.readLineSync()!.toUpperCase();
  }
}
Questão 16) Construa um algoritmo para ler o tamanho e os elementos de 4 vetores e responda: a) Gere um quinto vetor com os valores dos outros vetores de forma ordenada. b) Gere um vetor só com os elementos que tenham interseção com os 4 vetores.
import 'dart:io';
 
List<int> lerVetor(int num) {
  print('Tamanho do vetor $num:');
  int t = int.parse(stdin.readLineSync()!);
  List<int> v = [];
  for (int i = 0; i < t; i++) {
    print('Elemento ${i + 1}:');
    v.add(int.parse(stdin.readLineSync()!));
  }
  return v;
}
 
void main() {
  List<int> v1 = lerVetor(1);
  List<int> v2 = lerVetor(2);
  List<int> v3 = lerVetor(3);
  List<int> v4 = lerVetor(4);
 
  // a)
  List<int> v5 = [];
  v5.addAll(v1);
  v5.addAll(v2);
  v5.addAll(v3);
  v5.addAll(v4);
 
  for (int i = 0; i < v5.length; i++) {
    for (int j = i + 1; j < v5.length; j++) {
      if (v5[i] > v5[j]) {
        int aux = v5[i];
        v5[i] = v5[j];
        v5[j] = aux;
      }
    }
  }
  print('Vetor ordenado: $v5');
 
  // b)
  List<int> inter = [];
  for (var x in v1) {
    if (v2.contains(x) && v3.contains(x) && v4.contains(x) && !inter.contains(x)) {
      inter.add(x);
    }
  }
  print('Intersecao: $inter');
}
Questão 17) Faça um algoritmo utilizando procedimento ou funções que leia dois vetores, gere e imprima um terceiro vetor que seja a soma dos dois vetores lidos e imprima também a soma de todos os elementos deste 3º vetor.
import 'dart:io';
 
List<int> lerVetor(int t) {
  List<int> v = [];
  for (int i = 0; i < t; i++) {
    print('Elemento ${i + 1}:');
    v.add(int.parse(stdin.readLineSync()!));
  }
  return v;
}
 
List<int> somaVetores(List<int> a, List<int> b) {
  List<int> c = [];
  for (int i = 0; i < a.length; i++) {
    c.add(a[i] + b[i]);
  }
  return c;
}
 
int somaElementos(List<int> v) {
  int soma = 0;
  for (var x in v) {
    soma = soma + x;
  }
  return soma;
}
 
void main() {
  print('Tamanho dos vetores:');
  int t = int.parse(stdin.readLineSync()!);
 
  print('Vetor 1:');
  List<int> v1 = lerVetor(t);
  print('Vetor 2:');
  List<int> v2 = lerVetor(t);
 
  List<int> v3 = somaVetores(v1, v2);
  print('Terceiro vetor: $v3');
  print('Soma dos elementos: ${somaElementos(v3)}');
}

