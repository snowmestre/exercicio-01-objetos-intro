# exercicio-01-objetos-intro

## Implementar o modelo

O modelo definido nos casos de teste a seguir especifica a inicialização (construção), estado inicial, operações e estados esperados. Implemente conforme os testes.

Casos de teste:
```java
RadioFM radio = new RadioFM("Pionner", 100, 4); // Pionner 100W (4 saídas de 25w)
System.out.println(radio.fabricante); // Pionner
System.out.println(radio.potenciaTotal); // 100
System.out.println(radio.saidas); // 4
System.out.println(radio.potenciaSaida); // 25
System.out.println(radio.frequencia); // 76.1   (de 76.1 a 108.1MHz)
System.out.println(radio.volume); // 10 (de 0 a 100%)

radio.aumentarVolume(); // +1 vol
System.out.println(radio.volume); // 11
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
System.out.println(radio.volume); // 15

radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia); // 76.3
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia); // 77.1

// Casos excepcionais
while (radio.frequencia < 107) radio.avancaSintonia();

System.out.println(radio.frequencia); // 107.1
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia); // 108.1
radio.avancaSintonia(); // +0.2 freq (rodar a freq)
System.out.println(radio.frequencia); // 76.1

while(radio.volume < 100) radio.aumentarVolume();

System.out.println(radio.volume); // 100
radio.aumentarVolume(); // +1 vol (máx 100)
System.out.println(radio.volume); // 100
```

Agora, a segunda parte exige que o Radio seja aprimorado para passar nos seguintes testes:

```java
RadioFM radio = new RadioFM("Philips", 180, 6); // Pionner 100W (4 saídas de 25w)
System.out.println(radio.fabricante); // Philips
radio.fabricante = "Samsung"; // não deve ser possível, comente essa linha
System.out.println(radio.potenciaTotal); // 180
radio.potenciaTotal = 200; // não deve ser possível, comente essa linha
System.out.println(radio.saidas); // 6
radio.saidas = 10; // não deve ser possível, comente essa linha
System.out.println(radio.potenciaSaida); // 30
radio.potenciaSaida = 50; // não deve ser possível, comente essa linha
System.out.println(radio.frequencia()); // 76.1   (de 76.1 a 108.1MHz)
System.out.println(radio.volume()); // 10 (de 0 a 100%)

radio.frequencia = 70; // não deve ser possível, comente essa linha
radio.volume = 200; // não deve ser possível, comente essa linha

radio.aumentarVolume(); // +1 vol
System.out.println(radio.volume()); // 11
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
radio.aumentarVolume(); // +1 vol
System.out.println(radio.volume()); // 15

radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia()); // 76.3
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia()); // 77.1

// Casos excepcionais
while (radio.frequencia() < 107) radio.avancaSintonia();

System.out.println(radio.frequencia()); // 107.1
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
radio.avancaSintonia(); // +0.2 freq
System.out.println(radio.frequencia()); // 108.1
radio.avancaSintonia(); // +0.2 freq (rodar a freq)
System.out.println(radio.frequencia()); // 76.1

radio.frequencia(102.1);
System.out.println(radio.frequencia()); // 102.1

radio.frequencia(110.1);
System.out.println(radio.frequencia()); // 102.1

radio.frequencia(95.3);
System.out.println(radio.frequencia()); // 95.3
radio.salvarEstacao(1);

radio.frequencia(97.1);
System.out.println(radio.frequencia()); // 97.1
radio.salvarEstacao(2);

radio.carregarEstacao(1);
System.out.println(radio.frequencia()); // 102.1
radio.carregarEstacao(2);
System.out.println(radio.frequencia()); // 97.1
radio.carregarEstacao(3);
System.out.println(radio.frequencia()); // 97.1

while(radio.volume() < 100) radio.aumentarVolume();

System.out.println(radio.volume()); // 100
radio.aumentarVolume(); // +1 vol (máx 100)
System.out.println(radio.volume()); // 100


radio.baixarVolume();
System.out.println(radio.volume()); // 99

System.out.println(radio.silenciar());
System.out.println(radio.volume()); // 0
System.out.println(radio.silenciar());
System.out.println(radio.volume()); // 99
```

## Modelar um objeto e implementar

Escrever os testes declarando a inicialização (construção), estado inicial, operações, estados esperados.
