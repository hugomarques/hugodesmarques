---
layout: post
title:  "Java Libs: Introdução ao Lombok"
date:   
categories: java libs
comments: true 
---

Java sempre foi conhecida como uma linguagem lenta e verborágica. Apesar de muitas dessas afirmações serem devido a falta de conhecimento ou estigma herdado das primeiras versões da JVM outras tanta ainda são verdade. Para quem vem de outras linguagens como Python ou Ruby é fato que em Java, tal como o português, muitas vezes se escreve muito para se fazer pouco.
Recentemente diversas APIs e libs estão surgindo para minimizar o esforço de escrever código Java e tornar a linguagem algo mais produtivo para o desenvolvedor, Lombok é uma dessas libs.

##O que é Lombok?

Lombok é um jar que quando adicionado ao seu classpath permite o use de annotations para descrever diversos comportamentos comuns e um tanto repetitivos na linguagem.
Esse tutorial serve como uma rápida introdução à API, para maiores detalhes, veja as fontes no final desse artigo.

##Mãos à obra

###@NonNull

```Java

public Creature getInstanceOf(@NonNull String name, 
	@NonNull CreatureType creatureType) {
	return new Creature(name, creatureType);
}
```

Como você já deve suspeitar, caso você tente usar o método acima passando name ou creatureType com valor null, ele irá lançar uma NullPointerException. 

###@Getter @Setter


#### Field level ####

```Java
public class Creature {
	@Getter //Cria automaticamente um método public String getName() para a class Creature.
	String name;
	/* Cria automaticamente um método public CreatureType getType() para a class Creature.
	 * Cria automaticamente um método public void setType(CreatureType type) para a class Creature.
	*/
	@Getter @Setter 
	CreatureType type;	
}
```

#### Class level ####
```Java
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
```

###@EqualsAndHashCode

```Java
/* Esqueça seu gerador de equals e hashcode da sua IDE. 
 * A anotação abaixo gera exatamente esse código para você.
 * Outras opções são possíveis como excluir atributos, para mais detalhes verifique o site do projeto.
*/
@EqualsAndHashCode
public class Creature {
	String name;
	CreatureType type;	
}
```

###@Data

```Java
/* Mais conhecida como adeus java bean verborágico.
 * A anotação abaixo é o mesmo de você anotar sua classe com @Getter @Setter @EqualsAndHashCode
 *
*/
@Data
public class Creature {
	String name;
	CreatureType type;	
}
```

é o mesmo que: 

```Java
@EqualsAndHashCode
@Getter
@Setter
public class Creature {
	String name;
	CreatureType type;	
}
```

###@AllArgsConstructor

###@Slf4j

###@Builder

##Polêmicas

Como n

##Conclusão

See more at www.projectlombok.org

Fontes

https://projectlombok.org/
http://jnb.ociweb.com/jnb/jnbJan2010.html


