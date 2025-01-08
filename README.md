# kotlin-00-e-modificadores-de-acesso

Vamos abordar cada ponto detalhadamente, com exemplos e explicações claras.

---

### **Modificadores de Acesso**
Os modificadores de acesso controlam a visibilidade e o acesso a classes, funções, propriedades e outros elementos em Kotlin e Java. Eles são importantes na **Orientação a Objetos (OO)** para:

- Encapsular dados e comportamentos.
- Garantir que apenas partes específicas do código acessem certos elementos.
- Aumentar a segurança e manutenibilidade do código.

#### Em Kotlin:
- **`public`**: Visível em qualquer lugar do projeto. É o padrão.
- **`private`**: Visível apenas dentro do arquivo ou classe onde foi declarado.
- **`protected`**: Visível na classe e em subclasses.
- **`internal`**: Visível apenas dentro do mesmo módulo.

No seu código:
```kotlin
private class Employee {

}
```
A classe `Employee` é privada, ou seja, só é acessível dentro do arquivo `accessmodifiers.kt`. Isso impede que qualquer outro arquivo veja ou utilize essa classe.

#### Em relação à herança:
Uma classe marcada como `private` não pode ser estendida fora de seu escopo visível, ou seja, apenas dentro do mesmo arquivo. Isso reforça o encapsulamento.

---

### **O que o código faz?**
1. A classe `Employee` é declarada como `private`. Isso significa que ela é acessível apenas dentro do arquivo `accessmodifiers.kt`.
2. No `main`, você cria uma instância da classe:
   ```kotlin
   val emp = Employee()
   ```
3. Quando você imprime `emp`, o método `toString()` é chamado. A saída padrão de `toString()` para uma classe que não sobrescreve esse método é algo como:
   ```
   NomeDoPacote.NomeDaClasse@HashCode
   ```
   No caso:
   ```
   academy.learnprogramming.accessmodifiers.Employee@3b95a09c
   ```
   Isso indica que o objeto pertence à classe `Employee` dentro do pacote `academy.learnprogramming.accessmodifiers`, e o hash (`3b95a09c`) representa a localização do objeto na memória.

---

### **Comparação com Java**
O mesmo código em Java ficaria assim:

```java
package academy.learnprogramming.accessmodifiers;

public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee();
        System.out.println(emp);
    }
}

class Employee {
}
```

Aqui está a diferença entre Kotlin e Java:
1. Em Kotlin, você não precisa de uma classe separada para o método `main`. Você pode escrever o método diretamente no arquivo.
2. O Kotlin usa menos boilerplate (código repetitivo). Note a ausência de palavras-chave como `public`, `static`, e `void` no Kotlin.
3. O Kotlin permite marcar a classe `Employee` como `private` no nível do arquivo, enquanto no Java, a classe só pode ser marcada como `private` se for uma classe aninhada.

A vantagem de Kotlin aqui é sua **simplicidade e menos verbosidade**. O mesmo comportamento é alcançado com menos código.

---

### **Sobre a classe `private class Employee`**
Essa é uma classe **nativa do Kotlin**, não do Java. Apesar disso, como Kotlin é interoperável com Java, a sintaxe e o comportamento podem parecer semelhantes. Em Java, marcar uma classe como `private` diretamente no nível do arquivo não é permitido. Isso só pode ser feito dentro de outra classe.

Exemplo inválido em Java:
```java
private class Employee {
}
```
Esse código geraria um erro de compilação em Java. Em Kotlin, no entanto, é perfeitamente válido.

---
