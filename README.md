# AtividadeOscar_SQL

1) Quantas vezes natalie portman foi indicada ao oscar? <br>
R: Foi indicada 3 vezes.<br>

```sh 
select * from movies where name= "natalie portman";
```

2) Quantos oscars natalie portman ganhou?<br>
 R: Ganhou 1 vez.<br>
```sh 
select * from movies where name = "natalie portman" and winner= "true";
``` 

3) Amy Adams já ganhou algum oscar?<br>
  R: Não.<br>
```sh 
select * from movies where name = "amy adams" and winner = "true";
```

4) Toy Story 3 ganhou um oscar em quais anos?<br>
  R:Ganhou 1 oscar na categoria "animated feature film" e 1 oscar na categoria "music (original song)".<br>
```sh 
select * from movies where film = "toy story 3";
```

5) Quem tem mais oscars: a categoria "melhor ator" ou "melhor filme"?<br>
  R: Categoria "melhor ator" tem 49 oscars e categoria "melhor filme" tem 58 oscars.<br>
```sh 
select count(*) as oscars_melhor_ator from movies where category = "actor"  and winner = "1"; 

select count(*) as oscars_melhor_filme  from movies where category = "best picture" and winner = "1";

```


6) Na coluna/campo winner, altere todos os valores com "true" para 1 e todos os valores "false" para 0.<br>
```sh 
update movies set winner = "0" where winner = "false";

update movies set winner = "1" where winner = "true";
```

 8) Em qual edição do oscar "crash" ganhou o prêmio principal?<br>
 R: Ganhou na edição 78.<br>
 ```sh 
select * from movies where film = "crash";
```

 9) Bom... dê um oscar para um filme que merece muito, mas não ganhou.<br>
 ```sh 
update movies set winner = "1" where film = "the noose";
```

 10) O filme central do brasil aparece no oscar?<br>
  R: Não<br>
  ```sh 
select * from movies where film = "central do brasil";
```

11) Inclua no banco 3 filmes que nunca nem foram nomeados ao oscar, mas que na sua opinião, merecem.<br> 
  ```sh 
insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2014, 2015, 87, 'best picture', 'the grand budapest hotel', 'o grande hotel budapeste', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2011, 2012, 84, 'best picture', 'drive', 'drive', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2013, 2014, 86, 'best picture', 'inside llewyn davis', 'inside llewyn davis - balada de um homem comum', '0');
  ```

 12) Crie uma nova categoria de premiação. qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.<br> 
  ```sh 
update movies set category = 'best production design' where film = 'o grande hotel budapeste';

update movies set category = 'best production design' where film = 'drive';

update movies set category = 'best production design' where film = 'inside llewyn davis - balada de um homem comum';
  ```

 13) Qual foi o primeiro ano a ter um prêmio do oscar?<br> 
 R: Ano de 1928.<br> 
   ```sh 
select * from movies where winner = '1' order by ceremony asc ;
  ```

14) Pensando no ano em que você nasceu: qual foi o oscar de melhor filme, melhor atriz e melhor diretor?<br> 
  R: A única categoria que ganhou foi melhor diretor:"art direction:  john myhre; set decoration:  gordon sim".<br> 
```sh 
select * from movies where year_ceremony  = "2003" and winner = "0" and category = "actor";

select * from movies where year_ceremony  = "2003" and winner = "0" and category = "actress";

select * from movies where year_ceremony  = "2003" and winner = "1" and category = "art direction";
   ```

 15) Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o oscar. só foram nomeados. <br>
   ```sh 
insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2003, 2004, 76, 'best supporting actress', 'shohreh aghdashloo', 'house of sand and fog', '0'); 

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2006, 2007, 79, 'best supporting actress', 'rinko kikuchi', 'babel', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2004, 2005, 77, 'best actress', 'catalina sandino moreno', 'maria full of grace', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2018, 2019, 91, 'best actress', 'yalitza aparicio', 'roma', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2011, 2012, 84, 'best supporting actress', 'bérénice bejo', 'the artist', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2008, 2009, 81, 'best supporting actress', 'viola davis', 'doubt', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2002, 2003, 75, 'best actress', 'salma hayek', 'frida', '0');
   ```

16) Agora vamos falar da sua vida. Me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. Agora me diz: quê prêmio essa pessoa merece? <br>
 R: Minha mãe, Inacia, é a pessoa que mais me incentiva a querer crescer profissional e pessoalmente.

