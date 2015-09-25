---
layout: post
title:  "Java Libs: Introdução ao Lombok"
date: 2015-09-08 00:00:00
categories: java lib
comments: true
---
Java sempre foi conhecida como uma linguagem lenta e verborágica. Apesar de muitas dessas afirmações serem devido ao estigma herdado das primeiras versões da JVM, outras tanta ainda são verdade. Para usuários de outras linguagens, como Python ou Ruby, é fato que em Java, tal como o português, muitas vezes se escreve muito para se "falar" pouco.

Recentemente diversas APIs e libs estão surgindo para minimizar o esforço de escrever código Java e tornar a linguagem algo mais produtivo para o desenvolvedor, Lombok é uma dessas libs.

##O que é Lombok?

Lombok é uma lib disponibilizada no formato de jar que quando adicionado ao seu classpath permite o use de annotations para descrever diversos comportamentos comumente usados na linguagem.

Esse tutorial serve como uma rápida introdução à API, para maiores detalhes, veja as fontes no final desse artigo.

##Mãos à obra

###@NonNull

{%highlight java linenos %}

public Creature getInstanceOf(@NonNull String name, 

	@NonNull CreatureType creatureType) {
		return new Creature(name, creatureType);
	}

}
{% endhighlight %}


Como você já deve suspeitar, caso você tente usar o método acima passando name ou creatureType com valor null, ele irá lançar uma NullPointerException. 

###@Getter @Setter

#### Field level ####

{%highlight java linenos %}
public class Creature {
	@Getter //Cria automaticamente um método public String getName() para a class Creature.
	String name;
	/* Cria automaticamente um método public CreatureType getType() para a class Creature.
	 * Cria automaticamente um método public void setType(CreatureType type) para a class Creature.
	*/
	@Getter @Setter 
	CreatureType type;	
}
{% endhighlight %}

#### Class level ####
{%highlight java linenos %}
/* Cria automaticamente um método public String getName() para a class Creature.`
 * Cria automaticamente um método public void setName(String name) para a class Creature.
 * Cria automaticamente um método public CreatureType getType() para a class Creature.
 * Cria automaticamente um método public void setType(CreatureType type) para a class Creature.
 */
@Getter @Setter
public class Creature {
	
	String name;
	
	CreatureType type;	
}
{% endhighlight %}

###@EqualsAndHashCode

{%highlight java linenos %}
/* Esqueça seu gerador de equals e hashcode da sua IDE. 
 * A anotação abaixo gera exatamente esse código para você.
 * Outras opções são possíveis como excluir atributos, para mais detalhes verifique o site do projeto.
*/
@EqualsAndHashCode
public class Creature {
	String name;
	CreatureType type;	
}
{% endhighlight %}

###@ToString

{%highlight java linenos %}
/* Gera o método toString().
 * O método retorna a seguinte String: Creature(name, type). 
 * Outras opções são possíveis como excluir atributos, para mais detalhes verifique o site do projeto.
*/
@ToString
public class Creature {
	String name;
	CreatureType type;	
}
{% endhighlight %}

###@Data

{%highlight java linenos %}
/* Mais conhecida como adeus java bean verborágico.
 * A anotação abaixo é o mesmo de você anotar sua classe com @Getter @Setter @EqualsAndHashCode @ToString
 *
*/
@Data
public class Creature {
	String name;
	CreatureType type;	
}
{% endhighlight %}

é o mesmo que: 

{%highlight java linenos %}
@EqualsAndHashCode
@Getter
@Setter
public class Creature {
	String name;
	CreatureType type;	
}
{% endhighlight %}

###@AllArgsConstructor

{%highlight java linenos %}
/*
 * A anotação abaixo gera um construtor do tipo:
 * public Creature(Strine name, CreatureType type) {
 * 	this.name = name;
 * 	this.type = type;
 * }
 * Mais opções estão disponível, como exclusão de atributos.
 * Consulte a documentação para mais detalhes.
 */
@AllArgsConstructor
public class Creature {
	String name;
	CreatureType type;	
}
{% endhighlight %}

###@Slf4j

{%highlight java linenos %}
/*
* Essa anotação gera um atributo log que pode ser usado no código.
*/
@Slf4j
public class CreatureResource {

	/* O código abaixo não gera erro de compilação.
	* A variável é criada pela annotation, similar a linha: 
	* private static final org.slf4j.Logger log = org.slf4j.LoggerFactory.getLogger(CreatureResource.class);
	*/
	public void doGet() {
		log.info("Entrei no doGet");
	}
	
}
{% endhighlight %}

##E ainda tem mais...

As anotações demonstradas aqui possuem diversas configurações possíveis. Além disso, inúmeras outras annotations existem, por exemplo [@Builder](https://projectlombok.org/features/Builder.html) que implementa o Design Pattern de mesmo nome.
Não quis me aprofundar pois acredito que o material oficial e o excelente artigo no final desse post são mais do que suficientes.

##Polêmicas
Por fim, não posso deixar de mencionar que inúmeras pessoas são contra o uso de ferramentas como Lombok. Um dos principais argumentos cita que annotations são formas de se construir meta-data em cima de Java e não implementar novas funcionalidades através de geração de código. Por exemplo, se você remover a annotation @Slf4j o código para de compilar, diferente do que aconteceria se você removesse uma annotation @Entity de um bean qualqer.

##Conclusão
No meu dia a dia tenho achado o Lombok uma ferramenta extremamente produtiva que quando bem usada ajuda bastante a diminuir o trabalho repetitivo do programador.

Como toda boa ferramenta, deve ser usado sem abuso. Particularmente, eu evito usar @Data pois não gosto de expôr meus sets, além disso, implementações do equals e do hashcode gerados devem ser validados através de unit tests para garantir que o comportamento é o esperado pelo desenvolvedor.

Espero que tenham gostado do post e fico no aguardo de dúvidas e sugestões nos comentários. Maiores detalhes sobre a lib podem ser achados nos links abaixo.

## Fontes

1. <https://projectlombok.org/>
2. <http://jnb.ociweb.com/jnb/jnbJan2010.html>



