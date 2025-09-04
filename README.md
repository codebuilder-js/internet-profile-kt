## 📌 Descrição Geral

Este programa define uma classe `Person` que representa uma pessoa, contendo nome, idade, hobby e um possível "referenciador" (ou seja, outra pessoa que a indicou).
Ele permite exibir perfis detalhados, incluindo informações do referenciador e seu hobby.

---

## 📂 Estrutura do Código

### Classe `Person`

```kotlin
class Person(
    val name: String,
    val age: Int,
    val hobby: String?,
    val referrer: Person?
) {
    fun showProfile() {
        println("Name: $name")
        println("Age: $age")
        
        if(hobby != null) {
            print("Likes to $hobby. ")
        }
        
        if(referrer != null) {
            print("Has a referrer named ${referrer.name}")
            
            if(referrer.hobby != null) {
                print(", who likes to ${referrer.hobby}.")
            } else {
                print(".")
            }
        } else {
            print("Doesn't have a referrer.")
        }
        
        print("\n\n")
    }
}
```

#### 🔑 Propriedades

* `name: String` → nome da pessoa.
* `age: Int` → idade.
* `hobby: String?` → hobby opcional da pessoa.
* `referrer: Person?` → pessoa que serviu como referência, podendo ser `null`.

#### 👤 Método

* `showProfile()`

  * Exibe no console um resumo do perfil:

    * Nome e idade.
    * Hobby (se existir).
    * Referenciador, incluindo hobby do referenciador (se existir).

---

### Função `main()`

```kotlin
fun main() {
    val amanda = Person("Amanda", 33, "play tennis", null)
    val atiqah = Person("Atiqah", 28, "climb", amanda)
    
    amanda.showProfile()
    atiqah.showProfile()
}
```

* Cria duas pessoas:

  * `Amanda` → tem hobby, mas não tem referenciador.
  * `Atiqah` → tem hobby e tem `Amanda` como referenciadora.
* Chama `showProfile()` para exibir informações de cada uma.

---

## ✅ Exemplo de Saída

```
Name: Amanda
Age: 33
Likes to play tennis. Doesn't have a referrer.

Name: Atiqah
Age: 28
Likes to climb. Has a referrer named Amanda, who likes to play tennis.
```

---
