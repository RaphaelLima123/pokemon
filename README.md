# pokemon
Atividade do professor Diego

1.	Selecione o banco de dados (esquema) pokédex.

```SQL
USE pokedex;

```
2.	Obtenha informações da estrutura da tabela Pokémon.
```SQL
USE pokedex;
DESC pokemon;
```
3.	Selecione todos os pokémons cadastrados no banco de dados.
```SQL
USE pokedex;
SELECT * FROM pokemon
```
4.	Selecione o numero, nome, cor, altura_m e peso_kg de todos os pokémons cadastrados.
```SQL
USE pokedex;
SELECT  numero, cor, altura_m, peso_kg FROM pokemon;
```

5.	Qual é o numero e o nome de todos os pokémons da primeira geração?
```SQL
USE pokedex;
SELECT  numero, nome FROM pokemon WHERE geracao = 1;
```
6.	Quais são os pokémons Amarelo da primeira geração?
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE cor = 'Amarelo' AND geracao = 1;
```
7.	Qual é o pokémon mais forte?
```SQL
USE pokedex;
SELECT nome FROM pokemon ORDER BY total DESC LIMIT 1;
```
8.	Selecione o numero, nome e tipo1; de todos os pokémons cujo tipo primário é Fire.
```SQL
USE pokedex;
SELECT numero, nome, tipo1 FROM pokemon WHERE tipo1 = 'Fire';
```
10.	Selecione em ordem decrescente o numero, nome e defesa de todos os pokémons.
```SQL
USE pokedex;
SELECT numero, nome, defesa FROM pokemon ORDER BY defesa DESC;
```
11.	Qual o pokémon possui menor taxa de captura? Selecione apenas numero e nome.
```SQL
USE pokedex;
SELECT numero, nome FROM pokemon ORDER BY taxa_captura ASC LIMIT 1;
```
12.	Selecione todos pokémons que não possuem tipo secundário, ou seja, tipo2.
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE tipo2 IS NULL;
```
13.	Selecione numero, nome, tipo1, tipo2 de todos os pokémons que possuem o peso entre 100kg e 500kg.
```SQL
USE pokedex;
SELECT numero, nome, tipo1, tipo2 FROM pokemon WHERE peso_kg > 100 AND peso_kg < 500;
```
14.	Crie um ranking dos top 10 pokémons mais velozes, contendo numero, nome e velocidade.
```SQL
USE pokedex;
SELECT numero, nome, velocidade FROM pokemon ORDER BY velocidade DESC LIMIT 10;
```
15.	Selecione numero, nome, tipo1, tipo2, taxa_captura dos pokémons que possuem os dois tipos e tenham uma taxa de captura acima de 100. Ordene os resultados decrescente pela taxa de captura.
```SQL
USE pokedex;
SELECT numero, nome, tipo1, tipo2, taxa_captura FROM pokemon WHERE tipo1 IS NOT NULL AND tipo2 IS NOT NULL AND taxa_captura > 100; 
```
16.	Quais são os tipos primários dos pokémons?
```SQL
USE pokedex;
SELECT tipo1 FROM pokemon GROUP BY tipo1; 
```
17.	Selecione o numero, nome e cor; de todos os pokémons que o nome começa com a letra D.
```SQL
USE pokedex;
SELECT numero, nome, cor FROM pokemon WHERE nome LIKE 'D%'; 
```
18.	Qual é o pokémon mais poderoso de todas as gerações?
```SQL
USE pokedex;
SELECT nome FROM pokemon ORDER BY total ASC LIMIT 1;
```
19.	Selecione o numero, nome, defesa, ataque dos pokémons com defesa > 60 e ataque <= 70; ordenados decrescente pelo total.
```SQL
USE pokedex;
SELECT numero, nome, defesa, ataque FROM pokemon WHERE defesa > 60 AND  ataque <= 70 ORDER BY total ASC;
```
20.	Selecione todos os pokémons do tipo Planta e Venenoso que não sejam Green, ordenado crescente pelo nome.
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE tipo1 = 'Planta' OR tipo1 = 'Venenoso' AND cor != 'Green' ORDER BY nome;
```
21.	Selecione de maneira crescente os nomes dos pokémons que possuem a letra y na 4ª posição do nome.
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE nome LIKE '___Y' ORDER BY nome;
```
22.	Qual é o maior valor de ataque_especial cadastrado?
```SQL
USE pokedex;
SELECT ataque_especial FROM pokemon ORDER BY ataque_especial DESC;
```
23.	Selecione o numero, nome e altura_m dos pokémons que possuem altura acima de 2,10m.
```SQL
USE pokedex;
SELECT numero, nome, altura_m FROM pokemon WHERE altura_m > 2.10;
```
24.	Quais são as diferentes tipos de cores dos pokémons? Apresente os resultados de maneira crescente pelo nome da cor.
```SQL
USE pokedex;
SELECT cor FROM pokemon GROUP BY cor ORDER BY cor;
```
25.	Selecione o nome e velocidade dos pokémons com velocidade entre 30 e 70. Ordene os resultados por nome (crescente) e velocidade (decrescente)
```SQL
USE pokedex;
SELECT nome, velocidade FROM pokemon WHERE velocidade > 30 AND velocidade < 70 ORDER BY nome, velocidade DESC;
```
26.	Quem são os pokémons lendários? Apresente os resultados ordenados por total decrescente.
```SQL
USE pokedex;
SELECT nome, total from pokemon WHERE lendario = 1 ORDER BY total DESC;
```
27.	Selecione os pokémons da primeira geração com taxa de captura igual a 255.
```SQL
USE pokedex;
SELECT nome from pokemon WHERE taxa_captura = 255 AND geracao = 1;
```
28.	Quem é o mais poderoso? selecione o Pikachu, Squirtle, Bulbasaur e Charmander; ordenados decrescente pelo total.
```SQL
USE pokedex;
SELECT * FROM pokemon WHERE nome IN ('Pikachu', 'Squirtle', 'Bulbasaur', 'Charmander') ORDER BY total DESC;
```
29.	Quem são os pokémons da primeira geração, que começam com a letra d e não possuem tipo secundário? Ordene os resultados crescente por taxa_captura e decrescente pelo total.
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE geracao = 1 AND tipo2 IS NULL AND nome LIKE '%D' ORDER BY taxa_captura, total DESC;
```
30.	Qual é o ranking dos top 5 pokémons lendários com maior taxa_captura e total? Apresente apenas numero, nome, total, taxa_captura nos resultados.
```SQL
USE pokedex;
SELECT numero, nome, total, taxa_captura FROM pokemon WHERE lendario = 1 ORDER BY taxa_captura DESC, total DESC LIMIT 5;
```
31.	Selecione o numero, nome, peso_kg dos pokémons com peso entre 2kg e 3kgs?
```SQL
USE pokedex;
SELECT numero, nome, peso_kg  FROM pokemon WHERE peso_kg < 3 AND peso_kg > 2;
```
32.	Selecione o numero, nome, tipo1 e tipo2 dos pokémons com tipo primário Normal, que não possuem tipo secundário. Existe algum pokémon lendário nos resultados, se sim, os remova dos resultados?
```SQL
USE pokedex;
SELECT numero, nome, tipo1, tipo2  FROM pokemon WHERE tipo1 = 'Normal' AND tipo2 IS NULL AND LENDARIO = 0;
```
33.	Quem são os pokémons do tipo Water que não são azuis? Apresente numero, nome, tipo1, tipo2 e cor, ordenados pelo nome de maneira crescente.
```SQL
USE pokedex;
SELECT numero, nome, tipo1, tipo2, cor  FROM pokemon WHERE tipo1 = 'Water' AND cor != 'Blue' ORDER BY nome;
```
34.	Crie um ranking dos top 10 pokémons mais lentos.
```SQL
USE pokedex;
SELECT nome FROM pokemon ORDER BY velocidade LIMIT 10;
```
35.	Selecione os pokémons cujo nome comece e termine com a letra a.
```SQL
USE pokedex;
SELECT nome FROM pokemon WHERE nome LIKE 'a%a';
```
36.	Quem são os pokémons do tipo Fire que não são vermelhos? Apresente numero, nome, tipo1, tipo2 e cor, ordenados pelo nome de maneira crescente.
```SQL
USE pokedex;
SELECT numero, nome, tipo1, tipo2, cor FROM pokemon WHERE tipo1 = 'Fire' AND cor != 'Red' ORDER BY nome;
```
37.	Quais são os diferentes tipos de peso_kg dos pokémons? Apresente os resultados ordenados de maneira crescente.
```SQL
USE pokedex;
SELECT peso_kg FROM pokemon GROUP BY peso_kg ORDER BY peso_kg;
```
38.	Selecione o numero, nome e hp dos pokémons com valores entre 0 e 100. Ordene os resultados de maneira crescente por hp e nome.
```SQL
USE pokedex;
SELECT numero, nome, hp FROM pokemon WHERE hp > 0 AND hp < 100 ORDER BY hp, nome;
```
39.	Selecione o numero, nome, hp, ataque, defesa e total; dos pokémons com valores de hp, ataque, defesa maiores ou iguais a 100.
```SQL
USE pokedex;
SELECT numero, nome, hp, ataque, defesa, total FROM pokemon WHERE hp >= 100 AND ataque >= 100 AND defesa>= 100;
```
40.	Selecione todos os pokémons do tipos Water e Gelo, ordenados decrescente por total.
```SQL
USE pokedex;
SELECT * FROM pokemon WHERE tipo1 = 'Water' AND tipo2 = 'Gelo' OR tipo1 = 'Gelo' AND tipo2 = 'Water' ORDER BY total DESC;
```
